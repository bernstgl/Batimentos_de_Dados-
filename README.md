
# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# Projeto 

## 👨‍🎓 Integrantes:

<a href="https://www.linkedin.com/company/">Thiago Lima Bernardes</a>

### Coordenador(a)

- <a href="https://www.linkedin.com/in/profandregodoi/">André Godoi</a>

## 📜 Descrição

Objetivo geral da atividade:
Levantar, organizar e entender dados cardiológicos que, futuramente, alimentarão os módulos inteligentes do CardioIA.

Será necessária a preparação de três tipos de dados fundamentais:

- #1. Dados numéricos (simulados ou reais) relacionados a pacientes cardíacos;
- #2. Textos médicos ou literários relacionados à saúde cardiovascular;
- #3. Imagens médicas que representem exames ou sinais visuais do coração.


## 📁 Estrutura

- **Link One Drive com o dataset em formato ".csv":** 
- - https://fiapcom-my.sharepoint.com/:x:/g/personal/rm560085_fiap_com_br/EbLYIIOS3-ZIoAhzvf8PGtIByJ9Vo7H37WhQBixkTcrSfA?e=EB6Qsy
- **Textos médicos de J. Mitchell Bruce e Oliver T. Osborne sobre doenças do coração:**
- - https://fiapcom-my.sharepoint.com/:f:/g/personal/rm560085_fiap_com_br/EtPC9VEy_UlIlVWCbtJvauoBwL9XK5dawzA7_QHFdCmXHA?e=RsNiSZ
- **Diretório com as imagens médicas de exames do coração:**
- - https://fiapcom-my.sharepoint.com/:f:/g/personal/rm560085_fiap_com_br/El2pRhhuJTxLkgqwm8SFZlIBX0l_G4L37w4ZaPYhPNtrhg?e=IWo0j8
- **README.md**: Arquivo explicativo do projeto (o mesmo que você está lendo agora).
- **Docs**: Pasta com os documentos citados


## #1. Dados numéricos relacionados a pacientes cardíacos

### 📂 Origem do dataset

O arquivo "cardio_train.csv" é amplamente conhecido como parte do Cardiovascular Disease Dataset, disponibilizado publicamente no Kaggle e em competições de aprendizado de máquina.

Ele é derivado de um estudo populacional realizado pelo Instituto de Medicina Preventiva e Reabilitação em Moscou, Rússia (2010–2016).

O objetivo foi criar uma base de dados para testar modelos de predição de risco cardiovascular.

Portanto, não são dados sintéticos: são registros reais de pacientes, anonimizados e pré-processados para preservar privacidade.

O dataset contém 70 mil registros, cada linha representando um indivíduo.

### 📑 Principais variáveis

O dataset possui variáveis demográficas, clínicas e de estilo de vida. Vamos destacar as mais relevantes do ponto de vista clínico:

### age

Idade em dias (precisa ser convertida para anos).

Por que importa: idade é um dos fatores de risco mais fortes para doença cardiovascular — quanto maior, maior a probabilidade de eventos como infarto ou AVC.

### gender

1 = feminino, 2 = masculino.

- Por que importa: homens apresentam risco aumentado em idades mais jovens, enquanto mulheres têm risco crescente após a menopausa. É fundamental para estratificação de risco.

### ap_hi (pressão arterial sistólica) e ap_lo (pressão arterial diastólica)

Medidas da pressão arterial.

- Por que importa: hipertensão é um dos fatores mais fortes e modificáveis para risco de doença cardíaca, insuficiência cardíaca e AVC.

Valores anormais (ex.: >140/90) aumentam drasticamente o risco.

### cholesterol

1 = normal, 2 = acima do normal, 3 = muito acima do normal.

- Por que importa: hipercolesterolemia é fator de risco clássico para aterosclerose e infarto.

### gluc (glicose)

1 = normal, 2 = acima do normal, 3 = muito acima do normal.

- Por que importa: diabetes mellitus é fortemente associado a doenças cardiovasculares e acelera complicações ateroscleróticas.

### smoke (tabagismo)

0 = não, 1 = sim.

- Por que importa: tabagismo é um dos principais fatores de risco modificáveis.

### alco (consumo de álcool)

0 = não, 1 = sim.

- Por que importa: consumo abusivo de álcool aumenta risco de hipertensão, insuficiência cardíaca e arritmias.

### active (atividade física)

0 = não, 1 = sim.

- Por que importa: sedentarismo é fator de risco; atividade física regular protege contra eventos cardiovasculares.

### cardio (variável alvo)

0 = não tem doença cardiovascular, 1 = tem.

- Por que importa: é o rótulo que queremos prever com modelos de IA.

## 🩺 Variáveis mais relevantes (clínica + IA)

Destaques para um projeto de Inteligência Artificial voltado à saúde:

- Idade (age)

- Pressão arterial (ap_hi, ap_lo)

- Colesterol (cholesterol)

- Glicemia (gluc)

- Tabagismo (smoke)

- Atividade física (active)

Esses fatores compõem a base de praticamente todos os escores de risco cardiovascular clínicos (ex.: Framingham Risk Score, ESC SCORE2, ASCVD Risk Estimator).

### Eles são relevantes porque:

- São fatores de risco modificáveis → modelos de IA podem ajudar a prever risco e orientar intervenções.

- Permitem estratificação de pacientes em baixo, médio e alto risco.

- São dados fáceis de coletar em ambientes clínicos, favorecendo a aplicabilidade prática de um sistema de IA.


## #2. Textos médicos ou literários relacionados à saúde cardiovascular

📊 Exploração dos textos com algoritmos de NLP

Os dois textos escolhidos — Heart Disease in Middle and Advanced Age (Bruce, 1902) e Disturbances of the Heart (Osborne) — são fontes clássicas de conhecimento médico que descrevem sintomas, diagnósticos e tratamentos de doenças cardíacas. Embora antigos, eles oferecem uma base rica para experimentos de Processamento de Linguagem Natural (NLP).

A seguir, é descrito como cada técnica de NLP pode ser aplicada e por que é relevante para projetos de IA em saúde:

### 1. Extração de Sintomas e Condições

- O que fazer: usar Named Entity Recognition (NER) ou dicionários médicos para detectar termos relacionados a sintomas (ex.: “palpitation”, “dyspnea”, “angina”), sinais vitais, ou diagnósticos (“hypertension”, “valvular disease”).

### Por que é relevante:

- Permite criar bases de dados estruturadas a partir de textos não estruturados.

- Pode alimentar sistemas de apoio à decisão clínica, identificando sintomas em prontuários, artigos ou notas médicas.

- Ajuda a treinar modelos modernos em dados históricos, ampliando o vocabulário médico disponível para IA.

### 2. Classificação de Tópicos (Topic Modeling)

- O que fazer: aplicar técnicas como LDA (Latent Dirichlet Allocation) ou BERTopic para agrupar trechos em tópicos como:

- Etiologia (causas)

- Diagnóstico clínico

- Tratamento farmacológico

- Prognóstico e complicações

### Por que é relevante:

- Organiza o conteúdo em áreas temáticas, útil para sistemas de busca em saúde.

- Facilita revisões rápidas de literatura para médicos e pesquisadores.

- Permite comparar evolução de tópicos entre textos históricos e literatura moderna (ex.: como as causas atribuídas à insuficiência cardíaca mudaram ao longo do tempo).

### 3. Análise de Sentimentos e Polaridade

- O que fazer: identificar o tom do texto — positivo, negativo ou neutro — associado a diagnósticos e prognósticos.

Exemplo: trechos que descrevem sintomas graves geralmente carregam polaridade negativa (“grave”, “incurable”), enquanto orientações de tratamento podem ter polaridade positiva (“improvement”, “recovery”).

### Por que é relevante:

- Detecta nuances no discurso médico sobre risco ou esperança terapêutica.

- Pode ser usado em interfaces com pacientes para adequar linguagem de comunicação em relatórios ou chatbots de saúde.

- Ajuda a estudar o viés histórico na forma como certas doenças eram descritas (pessimismo em relação a sífilis cardíaca, otimismo com repouso ou dieta).

### 4. Construção de Ontologias Médicas

- O que fazer: extrair relações entre termos, por exemplo:

Sintoma → Doença (ex.: “dyspnea” → “heart failure”)

Doença → Tratamento (ex.: “angina” → “rest and diet”)

### Por que é relevante:

Cria grafos de conhecimento que podem ser usados para raciocínio automático em sistemas de IA.

Apoia o desenvolvimento de assistentes virtuais médicos mais inteligentes.

Facilita interoperabilidade com padrões de dados médicos modernos (ex.: SNOMED CT, UMLS).

### 5. Estudo de Evolução Linguística em Medicina

- O que fazer: comparar termos usados em 1902 com vocabulário moderno (ex.: “dropsy” hoje é “edema”).

### Por que é relevante:

- Ajuda a treinar algoritmos que precisam lidar com prontuários históricos digitalizados.

- Permite alinhar registros antigos com classificações modernas (CID-10 / CID-11).

- Contribui para preservação e atualização de conhecimento médico.

### 6. Aplicações Práticas em Projetos de IA na Saúde

- Chatbots clínicos: extrair sintomas relatados em linguagem natural de pacientes.

- Sistemas de triagem: mapear descrições de queixas em termos técnicos e classificar risco cardiovascular.

- Análise preditiva: correlacionar sintomas e fatores de risco descritos em textos históricos com dados atuais de pacientes.

- Educação médica: usar algoritmos de sumarização para produzir resumos acessíveis de literatura médica complexa.




## #3. Imagens médicas que representem exames ou sinais visuais do coração

As imagens estão organizadas em classes (stenosis e syntax) e representam exames de angiografia coronária ou similares, usados para avaliar doença arterial coronariana. Esses exames são fundamentais para diagnosticar estreitamento (estenose) e quantificar a complexidade das lesões (SYNTAX score).

Um sistema de IA com Visão Computacional (CV) pode atuar em diferentes níveis:

### 1. Detecção de padrões

- O que fazer: aplicar convoluções (CNNs) ou modelos baseados em transformers visuais (ViT) para identificar características recorrentes em imagens angiográficas, como:

- regiões mais escuras ou claras indicando fluxo de contraste;

- mudanças na espessura dos vasos;

- pontos de obstrução.

### Por que é relevante: Padrões de obstrução são frequentemente sutis e podem passar despercebidos por olhos inexperientes. Algoritmos podem capturar microcaracterísticas invisíveis a olho nu, aumentando a sensibilidade diagnóstica.

### 2. Identificação de bordas e segmentação

- O que fazer: utilizar algoritmos de detecção de bordas (Canny, Sobel, ou CNNs de segmentação como U-Net) para:

- delimitar os contornos das artérias;

- separar fundo e estruturas não relevantes;

- criar mapas de segmentação vascular.

### Por que é relevante: segmentar corretamente vasos é essencial para calcular métricas como diâmetro do lúmen, grau de estenose (%) e extensão da lesão. Isso fornece informações objetivas, consistentes e reprodutíveis.

### 3. Reconhecimento de anomalias

- O que fazer: treinar modelos de classificação e detecção para reconhecer:

- estenoses significativas (>70% da luz arterial);

- anomalias morfológicas (ramificações complexas, bifurcações, tortuosidades);

- lesões múltiplas (base para cálculo do SYNTAX score).

### Por que é relevante: a identificação automática de anomalias ajuda na triagem rápida de pacientes, priorizando casos mais graves e reduzindo a chance de erro humano.

### 4. Quantificação automática

- O que fazer: após segmentar vasos e localizar estenoses, algoritmos podem medir automaticamente:

- área do lúmen;

- grau percentual de obstrução;

- número e distribuição de lesões.

### Por que é relevante: fornece uma segunda opinião objetiva, reduz a variabilidade entre médicos e aumenta a confiança em decisões terapêuticas (ex.: angioplastia vs. cirurgia).

### 5. Aprendizado profundo e representação clínica

- O que fazer: usar deep learning supervisionado (classificação stenosis/syntax) ou não supervisionado (detecção de outliers) para criar representações latentes das imagens.

### Por que é relevante: essas representações podem ser integradas com dados clínicos (como os do cardio_train.csv) para gerar modelos híbridos de risco cardiovascular personalizado.

### 🩺 Importância para IA em Saúde

Diagnóstico precoce
→ Detectar estenoses antes que causem sintomas graves ou infarto.

Padronização clínica
→ Algoritmos reduzem variação entre médicos (interobservador).

Decisão terapêutica
→ Apoio no cálculo automático do SYNTAX score, que orienta se o paciente deve receber angioplastia ou cirurgia de revascularização.

Acesso ampliado
→ Em regiões com poucos especialistas, sistemas de IA podem dar suporte inicial, democratizando o diagnóstico.

Pesquisa e ensino
→ Modelos podem servir para treinar residentes de cardiologia com feedback automatizado.

## 🗃 Histórico de Lançamentos

- 1.0.0 - 02/09/2025

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>

