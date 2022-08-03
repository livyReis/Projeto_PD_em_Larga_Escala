# Especialização em Engenharia e Ciência de Dados promovida pela Universidade Federal de Pernambuco e Samsung(Sidi).

## Projeto Final da Disciplina de Processamento de Dados em Larga Escala - Corpus PT7 multiclasse

### Integrante: 
            Liviany Reis Rodrigues

### Contextualização:
O PT7 Web (https://ieee-dataport.org/open-access/pt7-web-annotated-portugueselanguage-corpus) é um Corpus anotado em língua portuguesa construído a partir de 
amostras coletadas de setembro de 2018 a março de 2020 de sete países de língua portuguesa: Angola, Brasil, Portugal, Cabo Verde, Guiné-Bissau, Macau e Moçambique. 
Os registros foram filtrados do Common Crawl — um conjunto de dados em escala de petabytes de domínio público de páginas da Web em vários idiomas, misturados em 
instantâneos temporais da Web, disponíveis mensalmente [1]. As páginas brasileiras foram rotuladas como classe positiva e as demais como classe negativa (português não 
brasileiro). O conjunto de dados totalizou 249,74 GB de texto HTML bruto relacionado a 16.346.693 páginas da web exclusivas. Os dados foram pré-processados para produzir vetores de distribuição de palavras de alta dimensionalidade (2 elevado a 18 = 262.144 características) como entrada para as fases de treinamento e teste. Uma demonstração do uso desses dados pode ser verificada em um projeto fracionário de dois níveis para investigar o desempenho do cluster no Spark.
Será utilizado um extrato reduzido do PT7 Web, equivalente 17014 páginas ~ 0.1% do Corpus original. Foram disponibilizados cinco arquivos (pt7-raw.zip), separados pelo
domínio de nível superior de cada país (.br, .pt, .mo, .gw, .mz, .ao e .pt).
Os dados se encontram rotulados como 1:pt_BR e 0:pt_OTHERS e estão disponível no formato a seguir, onde:
• label - rótulo 
• url - endereço original completo da página
• digest - uma função de bash do conteúdo da página
• raw - os dados brutos do texto da página após limpeza de tags HTML
### Etapa Preliminar :
Consiste em realizar o processo de ETL sobre os dados brutos, transformando o conteúdo de cada página web em um vetor esparso de características no formato exigido pelo Spark. A base deve separar os dados em novos rótulos, de acordo com cada país, formando uma base rotulada multiclasse.
### Modelo de Machine Learning - Random Forest
Random Forest: Random significa aleatório, e denota o comportamento do algoritmo ao selecionar subconjuntos de features e montar mini árvores de decisão. Forest significa floresta, já que são geradas várias árvores de decisão. Basicamente, o algoritmo possui 4 
passos:
1. Seleção aleatória de algumas features
2. Seleção da feature mais adequada para a posição de nó raiz
3. Geração dos nós filhos
4. Repete os passos acima até que se atinja a quantidade de árvores desejada
Depois que o modelo é gerado, as previsões são feitas a partir de “votações”. Cada mini 
árvore toma uma decisão a partir dos dados apresentados. A decisão mais votada é a 
resposta do algoritmo.

###OBS: No documento README_Projeto_final_PD_em_Larga_Escala.pdf é realizado o tutorial passo a passo de todas as etapas realizadas no projeto.
