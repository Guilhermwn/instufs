<template>
  <q-page class="q-pa-md">

    <div v-if="loading" class="row justify-center q-mt-lg">
      <q-spinner color="primary" size="3em" />
    </div>

    <!-- Seção de Professores -->
    <div v-if="professors.length" class="q-mb-lg">
      <h4 class="text-h5 q-mb-md">Professores</h4>
      <div class="row q-gutter-md">
        <q-card v-for="member in professors" :key="member.id" class="col-12 col-md-4">
          <q-img
            v-if="member.profile_image"
            :src="member.profile_image"
            alt="Foto de perfil"
            fit="cover"
            class="profile-image"
          />
          <q-card-section>
            <div class="text-h6">{{ member.name }}</div>
            <div class="text-subtitle2">{{ member.universityaffiliation }}</div>
          </q-card-section>

          <q-card-section>
            <p><strong>Departamento:</strong> {{ member.universitydepartment || 'Não informado' }}</p>
            <p><strong>Email:</strong> {{ member.email }}</p>
            <p><strong>Formação:</strong> {{ member.academicbackground || 'Não informado' }}</p>
          </q-card-section>

          <q-card-actions align="right">
            <q-btn v-if="member.curriculumlattes" color="primary" :href="member.curriculumlattes" target="_blank" label="Currículo Lattes" />
          </q-card-actions>
        </q-card>
      </div>
    </div>
    <!-- Seção de Professores -->

    <!-- Seção de Estudantes -->
    <div v-if="students.length">
      <h4 class="text-h5 q-mb-md">Estudantes</h4>
      <div class="row q-gutter-md">
        <q-card v-for="member in students" :key="member.id" class="col-12 col-md-4">
          <q-img
            v-if="member.profile_image"
            :src="member.profile_image"
            alt="Foto de perfil"
            fit="cover"
            class="profile-image"
          />
          <q-card-section>
            <div class="text-h6">{{ member.name }}</div>
            <div class="text-subtitle2">{{ member.universityaffiliation }}</div>
          </q-card-section>

          <q-card-section>
            <p><strong>Departamento:</strong> {{ member.universitydepartment || 'Não informado' }}</p>
            <p><strong>Email:</strong> {{ member.email }}</p>
            <p><strong>Formação:</strong> {{ member.academicbackground || 'Não informado' }}</p>
          </q-card-section>

          <q-card-actions align="right">
            <q-btn v-if="member.curriculumlattes" color="primary" :href="member.curriculumlattes" target="_blank" label="Currículo Lattes" />
          </q-card-actions>
        </q-card>
      </div>
    </div>
    <!-- Seção de Estudantes -->

  </q-page>
</template>

<script setup>
import { ref, onMounted } from "vue";

const members = ref([]);
const professors = ref([]);
const students = ref([]);
const loading = ref(true); // Adicionamos o estado de carregamento

const fetchMembers = async () => {
  try {
    const response = await fetch("https://instufs-fastapi.vercel.app/members", {
      method: "GET",
      headers: {
        "Content-Type": "application/json"
      },
    });

    if (!response.ok) {
      throw new Error("Erro ao buscar membros");
    }

    const data = await response.json();
    members.value = data;

    // Separar Professores e Estudantes
    professors.value = members.value.filter(m => m.occupation?.toLowerCase() === "professor");
    students.value = members.value.filter(m => m.occupation?.toLowerCase() === "estudante");

  } catch (error) {
    console.error("Erro:", error);
  } finally {
    loading.value = false;
  }
};

// Chama a API ao carregar o componente
onMounted(fetchMembers);
</script>

<style scoped>
.profile-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 8px 8px 0 0;
}
</style>
