<template>
  <q-page class="q-pa-md">
    <!-- CONTEÚDO PRINCIPAL DA PÁGINA INICIAL -->
    <!-- Sobre a Instrumentação -->
    <div class="q-pa-md">
      <h2 class="text-h4 text-title">SOBRE A INSTRUMENTAÇÃO</h2>

      <div class="image-container">
        <q-img
          src="img/logo-nome-azul.png"
          class="responsive-img"
          contain
        />
      </div>

      <p>
        O ser humano vem se utilizando de noções de medição desde o primeiríssimo momento em que decidiu olhar a
        natureza ao seu redor. A possibilidade de comparação entre elementos de forma a se atingir um valor numérico
        associado, ou seja, uma medida, tem causado importantes revoluções econômicas, técnicas e científicas ao longo
        dos séculos. A padronização desses elementos de comparação - com escalas, convenções e unidades - possibilitou,
        e ainda possibilita, um maior e melhor entendimento de resultados e análises de grandes descobertas feitas por
        todo o mundo. Um instrumento é o objeto utilizado para fazer uma medição e a Instrumentação Eletrônica diz
        respeito a todos os aspectos relacionados a instrumentos eletrônicos e suas medidas.
      </p>
      <p>
        Hoje em dia é quase impossível encontrar um setor industrial ou de pesquisa que não se utilize da
        instrumentação. São aparelhos, instrumentos, sensores e processos de aquisição e de controle de informações
        utilizados na área hospitalar, na construção civil, nas engenharias em geral, na medicina, na fisioterapia, na
        educação física, na computação, na eletrônica, na farmácia, na química, na física, etc. Onde for necessária a
        aferição de uma grandeza, estará presente a instrumentação. O desenvolvimento de pesquisas científicas e
        tecnológicas na área possibilita uma melhor formação de profissionais preparados para o mercado de trabalho
        industrial e acadêmico e para as alterações que ocorrem ao longo do tempo em áreas estratégicas.
      </p>
    </div>

    <!-- Sobre o Grupo de Pesquisa -->
    <div class="q-pa-md">
      <h2 class="text-h4 text-title">SOBRE O GRUPO DE PESQUISA</h2>
      <p>
        O Grupo de Pesquisa em Instrumentação Eletrônica foi formado oficialmente em 2016. Localizado principalmente no
        Departamento de Engenharia Elétrica da Universidade Federal de Sergipe (DEL-UFS), a Instrumentação tem a maioria
        das suas linhas de pesquisa voltadas ao sensoriamento e controle de sistemas diversos e à conversão
        analógico-digital. O grupo também segue o princípio de servir como suporte para trabalhos científicos e
        tecnológicos de toda a Universidade, tendo importantes parcerias com os departamentos de Fisioterapia (DFT-UFS),
        de Engenharia Civil (DEC-UFS), de Educação Física (DEF-UFS) e de Fisiologia (DFS-UFS).
      </p>
      <p>
        O grupo desenvolve seus trabalhos em três ambientes: a Sala do Grupo de Pesquisa em Instrumentação Eletrônica, o
        Laboratório de Instrumentação, Comunicações e Processamento de Sinais (LABCOM) e o Laboratório de Automação,
        Controle e Simulação (LACS).
      </p>
    </div>
  </q-page>
</template>

<script setup>
//
</script>


<style scoped>

.text-title{
  padding: 8px 0;
  margin: 20px 0;
  border-bottom: 2px solid #F1F0E9;
}


.image-container {
  display: flex;
  justify-content: center;
  margin-block: 30px;
}

.responsive-img {
  max-width: 70%;
}
</style>