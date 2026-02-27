# TrabalhoTC---Ot-vio
EDITOR DE AUTOMATOS E GRAMATICAS

Este projeto é um sistema interativo desenvolvido em Python para a criação, manipulação, simulação e conversão de Autômatos Finitos (Determinísticos e Não-Determinísticos) e Gramáticas Regulares. Ele serve como uma ferramenta educacional e prática para o estudo aprofundado de Teoria da Computação e Linguagens Formais.

AUTORES

Este projeto foi desenvolvido por:

Alexandre Melgaço Chaves Silva

Fabrício Cristian Formento de Sousa

Tadeu Henrique da Cruz Fernandes

FUNCIONALIDADES

O sistema oferece um menu interativo rodando direto no terminal, contendo um conjunto completo de ferramentas operacionais:

Manipulação de Autômatos (AFD e AFND)

Criação Personalizada: Definição interativa de estados, alfabeto, transições (incluindo transições vazias/incompletas e transições epsilon) e estados finais.

Exibição Acadêmica: Renderização de Tabelas de Transição formatadas usando a biblioteca pandas, idênticas às literaturas acadêmicas.

Simulação e Validação: Teste de palavras informadas pelo usuário com rastreamento visual do caminho percorrido (passo a passo dos estados ativos).

Conversão AFND para AFD: Implementação do algoritmo de Construção de Subconjuntos com suporte a Epsilon-Fecho. Inclui sistema de legenda automática para renomeação de estados compostos (ex: {q0, q1} -> Q1).

Minimização de AFD: Implementação do Algoritmo de Particionamento de Moore para redução do número de estados. O algoritmo inclui: preenchimento automático de funções parciais (criação de Estado Morto), remoção automática de estados inatingíveis via Busca em Largura, e legenda de fusão de estados equivalentes (ex: {q2, q3} -> M0).

Processamento de Gramáticas

Editor de Gramática Regular: Interface para entrada de produções Lineares à Direita no formato S -> aA | b | &.

Validação de Palavras (GR): Motor de validação de strings utilizando derivações a partir do símbolo inicial.

Árvore de Derivação: Geração e impressão visual no console da árvore sintática passo a passo para palavras aceitas pela Gramática Regular.

COMO EXECUTAR (GOOGLE COLAB / JUPYTER)

Este projeto foi desenvolvido em formato de Notebook (.ipynb), o que torna sua execução extremamente rápida e acessível diretamente pelo navegador.

Opção 1: Executando na Nuvem (Recomendado - Google Colab)
Esta é a forma mais simples de testar o sistema, pois não exige nenhuma instalação na sua máquina.

Faça o download do arquivo .ipynb deste repositório.

Abra o Google Colab (colab.research.google.com).

Vá em Arquivo > Fazer upload de notebook e selecione o arquivo baixado.

Com o projeto aberto, clique em Ambiente de execução > Executar tudo ou pressione Ctrl + F9.

Role até o final da página: o menu interativo aparecerá logo abaixo da última célula de código!

Opção 2: Executando Localmente
Caso prefira rodar o código na sua própria máquina:

Certifique-se de ter o Python 3.x e o gerenciador de pacotes pip instalados.

Instale a biblioteca necessária abrindo o terminal e digitando: pip install pandas

Abra o arquivo .ipynb utilizando o Jupyter Notebook, JupyterLab ou o VS Code (com a extensão Jupyter instalada).

Execute todas as células do notebook para iniciar o menu.

ESTRUTURA DO CODIGO

Para facilitar a navegação e futuras contribuições, aqui estão as principais funções do motor do sistema:

AutomatoFinitoDeterministico() e AutomatoFinitoNaoDeterministico(): Módulos de entrada de dados e formatação das regras do usuário.

ValidarPalavra(): Motor de processamento de strings da fita. Lida com o determinismo e simula o multiverso de estados do não-determinismo.

calcular_epsilon_fecho(): Função de suporte matemático para descobrir todos os estados alcançáveis via transições espontâneas (&).

conversao_afnd_para_afd(): Implementa a lógica de construção de subconjuntos mesclando os epsilon-fechos e renomeando as novas combinações.

minimizacao_afd(): Limpa estados inúteis, injeta estados sintéticos para completar a máquina e realiza a partição de estados equivalentes.

DefinirGramaticaRegular(): Analisa e valida a estrutura (sintaxe) das produções inseridas pelo usuário para garantir que são Lineares à Direita.

gerar_derivacao_linear_direita() e imprimir_arvore(): Utilizam recursão para testar caminhos de derivação e renderizam o resultado graficamente no console.
