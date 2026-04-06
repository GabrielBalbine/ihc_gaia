# 🧬 Projeto GAIA - Documentação de IHC

**Projeto:** GAIA (Visualização Computacional para Apoio ao Prognóstico de TEA)  
**Disciplina:** Interface Humano-Computador (IHC)  
**Semestre:** 2026

---

## 👥 Membros da Equipe

| Nome Completo | Matrícula |
| :--- | :--- |
| **[Gabriel Balbine de Andrades]** | [22.222.001-4] |

---

## 🚀 Entrega 1: Conhecendo o Problema (Definição do Escopo)
*Status: [Concluído]*

### 1.1) Membros de Equipe
*(Ver tabela acima)*

### 1.2) Título Original do TCC
> *ANÁLISE DE PADRÕES
COMPORTAMENTAIS NO TEA: DESAFIOS
DIAGNÓSTICOS E NOVAS FERRAMENTAS

TECNOLÓGICAS*

### 1.3) Nome do Orientador
* Prof. Victor Perrone Varela

### 1.4) Previsto desenvolver Interface?
- [x] Sim
- [ ] Não

### 1.5) Objetivo do trabalho?
Desenvolver uma solução tecnológica para **auxílio ao prognóstico**, processando vídeos de interações sociais para identificar padrões comportamentais típicos do espectro autista (como falta de contato visual e atenção compartilhada), fornecendo dados quantitativos para embasar a decisão médica.

### 1.6) Qual o produto final?
Um sistema desktop/web dividido em dois módulos distintos:
1.  **Módulo Admin (Dataset):** Para curadoria, ingestão de vídeos e refinamento do treinamento da IA.
2.  **Módulo Especialista (Clínico):** Para upload de vídeos de pacientes, análise pós-processada e visualização de dashboards de risco.

### 1.7) Quem é o usuário final deste produto?
Exclusivamente profissionais da saúde mental e pesquisadores:
* Psiquiatras
* Psicólogos / Neuropsicólogos
* Pesquisadores da área de neurodesenvolvimento

### 1.8) O que o usuário recebe de benefício ao usar esse produto?
O profissional ganha uma "segunda opinião" técnica baseada em métricas. A ferramenta destaca comportamentos sutis em vídeos (que poderiam passar despercebidos a olho nu) e gera um indicador de risco, servindo como um filtro objetivo para apoiar a elaboração do laudo clínico e justificar a necessidade de investigação aprofundada.

### 1.9) Quais as funcionalidades da ferramenta (visão do usuário)?
**Módulo Admin:**
* Ingestão de novos vídeos para o Dataset.
* Rotulagem e retreinamento do modelo.

**Módulo Especialista:**
* Upload de vídeos (análise assíncrona).
* Visualização do vídeo processado com *bounding boxes* (YOLO/MediaPipe).
* **Dashboard de Insights:** Gráficos de tempo de foco e contato visual.
* **Output de Decisão:** Indicador de "Probabilidade/Risco" sugerindo averiguação.

### 1.10) Quais tecnologias e ferramentas computacionais pretendem usar?
* **Backend/IA:** Python, YOLO (detecção), MediaPipe (Face Mesh/Pose).
* **Interface:** [Streamlit / React / Interface Web].
* **Infraestrutura:** Docker.

### 1.11) Qual é o contexto de uso dessa aplicação?
* **Ambiente:** Consultórios terapêuticos ou laboratórios de pesquisa (ambiente controlado).
* **Dinâmica:** Uso **assíncrono**. O profissional grava a sessão e submete o vídeo ao software posteriormente. A análise dos dados ocorre no computador do especialista durante a elaboração do laudo ou estudo do caso.

---

## 🔍 Entrega 2: Análise de Concorrência (Soluções Análogas)
*Status: [Concluído]*

### 1) Público Alvo
O sistema é destinado a **profissionais de saúde mental e pesquisadores** (Psiquiatras, Psicólogos, Neuropsicólogos) que buscam ferramentas de apoio à decisão clínica baseadas em evidências visuais quantitativas.

### 2) Análise de Concorrência

#### A. Principais Concorrentes (Referências de Interação)
| Nome | Área | Link | Descrição da Solução |
| :--- | :--- | :--- | :--- |
| **Aidoc** | Radiologia (IA) | [aidoc.com](https://www.aidoc.com/) | Plataforma de IA para radiologia que analisa imagens médicas (TC/Raio-X) para identificar anomalias agudas. Funciona como um sistema de triagem e priorização de lista de trabalho. |
| **Viz.ai** | Neurovascular (AVC) | [viz.ai](https://www.viz.ai/) | Utiliza IA para detectar sinais de AVC em tomografias computadorizadas e alerta a equipe médica em tempo real via aplicativo móvel, sincronizando o fluxo de cuidado. |
| **Lunit INSIGHT** | Oncologia | [lunit.io](https://www.lunit.io/) | Analisa imagens de Raio-X de tórax e mamografias para detectar nódulos e câncer, fornecendo uma pontuação de anormalidade e mapas de calor sobre a imagem. |

<img width="800" height="470" alt="image" src="https://github.com/user-attachments/assets/08ed6794-b6e5-418e-a7c0-fc6022d15193" />
<img width="800" height="470" alt="image" src="https://github.com/user-attachments/assets/7559989c-2b2d-4905-bb4f-e0d925bec94a" />
<img width="800" height="470" alt="image" src="https://github.com/user-attachments/assets/9dc5c312-fb08-4303-904d-b0b57bfd5355" />


#### B. Características e funcionalidades
* **Triagem Automatizada ("Always-on AI"):** (Aidoc/Viz.ai) O sistema monitora o fluxo de imagens do hospital 24/7 e processa tudo automaticamente, sem necessidade de clique manual.
* **Alertas Móveis:** (Viz.ai) Foco na mobilidade; envia notificações críticas para o smartphone do médico, permitindo visualização rápida da imagem processada.
* **Mapas de Calor (Heatmaps):** (Lunit) A IA não diz apenas "tem câncer"; ela colore a região suspeita com um mapa de calor, ajudando o médico a focar sua atenção imediatamente na área correta.
* **Score de Probabilidade:** (Todos) Fornecem uma porcentagem de certeza ou "grau de risco" para cada caso analisado.

#### C. Experiência do usuário (UX) e Opiniões
* **Explicação Visual (Explainability):** A grande força da UX dessas ferramentas é a sobreposição visual (overlays). O médico vê a imagem original com as anotações da IA por cima (bounding boxes ou cores), o que valida a decisão da máquina.
* **Priorização:** Em vez de analisar exames em ordem cronológica (fila comum), a interface reorganiza a lista colocando os casos críticos (detectados pela IA) no topo.
* **Simplicidade:** Interfaces limpas, geralmente em modo escuro (Dark Mode) para destacar o contraste das imagens médicas.

#### D. Preços e modelos de negócio
* **Modelo B2B/Enterprise:** Venda para hospitais e redes de saúde. Geralmente cobrado por volume de exames analisados ou assinatura anual da plataforma.

#### E. Padrões e tendências de mercado observadas
* **Suporte à Decisão (CDSS):** Consenso de mercado de que a IA é um "copiloto". A palavra final e o laudo são sempre humanos.
* **Visualização Mobile:** Tendência forte de permitir que o médico veja os resultados preliminares da IA no celular (tablet/smartphone) para agilizar a triagem.
* **Integração PACs:** As ferramentas não funcionam isoladas; elas injetam seus resultados diretamente nos visualizadores de imagem que os médicos já usam no dia a dia.

---
# 👤 Entrega 3: Personas e Contexto

**Status:** [Concluído]

## 1. Personas

### Persona Primária: Dra. Helena Souza
> **"A tecnologia deve ser uma lente de aumento para a intuição clínica."**

#### 1. Identidade

* **Nome:** Helena Souza.
* **Idade:** 42 anos.
* **Bio:** Possui doutorado em Psicologia Clínica com foco em TEA. Trabalha em clínica particular e Hospital Universitário há 15 anos. É extremamente técnica, mas sente o peso da rotina manual.
 <img width="512" height="512" alt="image" src="https://github.com/user-attachments/assets/b1bd22c1-2191-46a3-b289-9d6685ae45d2" />

#### 2. Status
* **Papel:** Neuropsicóloga Infantil e Pesquisadora./ Persona Primária
* **Nível de Influência:** Decisora (ela escolhe as ferramentas que usa).
* **Perfil Tecnológico:** Usuária Intermediária. Domina prontuários eletrônicos e Office, mas não sabe programar.

#### 3. Objetivos
* Reduzir a subjetividade ("achismo") na avaliação do contato visual.
* Obter métricas quantitativas precisas para embasar seus laudos.
* **Pessoal:** Otimizar o tempo burocrático para conseguir jantar com a família e descansar.

#### 4. Habilidades
* **Especialidade:** Expert em comportamento infantil e diagnóstico de TEA.
* **Competências:** Alta capacidade analítica clínica; Leitura de gráficos; Dificuldade com configurações técnicas complexas (instalação via terminal).

#### 5. Tarefas
* **Diárias:** Realizar sessões lúdicas e gravar vídeos; Revisar vídeos manualmente (ponto crítico).
* **Semanais:** Escrever laudos de evolução e dar devolutivas aos pais.

#### 6. Relacionamentos
* **Família (Marido e 2 filhos):** Motivação pessoal para buscar agilidade no trabalho.
* **Pacientes e Pais:** Foco de sua empatia profissional.
* **Colegas e Suporte de TI:** Interações pontuais na clínica.

#### 7. Requisitos
* **Interface:** Deve ser visual e intuitiva ("clicar e arrastar").
* **Performance:** Processamento em segundo plano sem travar o PC.
* **Segurança:** Sigilo absoluto dos vídeos.

#### 8. Expectativas
* Espera que o GAIA funcione como um "assistente residente" que faz o trabalho braçal.
* Espera que o sistema confirme sua intuição com dados concretos.

---

## 2. Mapa de Empatia (Dra. Helena)

| **O que ela VÊ?** | **O que ela OUVE?** |
| :--- | :--- |
| • Crianças com dificuldade de interação.<br>• Pais ansiosos por diagnósticos rápidos.<br>• Pilhas de anotações manuais.<br>• Colegas médicos usando IA em radiologia. | • Perguntas dos pais: "Ele melhorou mesmo?".<br>• O barulho da criança na sessão.<br>• Reclamações da família: "Você está trabalhando até tarde de novo?".<br>• Palestras sobre inovação na saúde. |
| **O que ela FALA e FAZ?** | **O que ela PENSA e SENTE?** |
| • Grava sessões no tripé.<br>• Assiste vídeos de madrugada pausando frame a frame.<br>• Busca ferramentas que automatizem a contagem.<br>• Tenta explicar a evolução clínica sem números concretos. | • **Preocupação:** "Será que perdi algum detalhe no vídeo?"<br>• **Frustração:** Sente-se uma "secretária de luxo" fazendo anotações manuais.<br>• **Desejo:** Quer focar no tratamento, não na burocracia.<br>• **Esperança:** Acredita que a tecnologia pode validar seu trabalho. |

### Dores e Necessidades

| **DORES (Pains)** | **NECESSIDADES (Gains)** |
| :--- | :--- |
| • **Medo do Erro:** Insegurança de basear um laudo médico apenas na memória ou anotações manuais.<br>• **Exaustão:** Cansaço mental extremo por ter que analisar vídeos longos repetidamente.<br>• **Culpa:** Sentimento de estar negligenciando a família por levar trabalho para casa.<br>• **Ineficiência:** Perder horas somando minutos em planilhas Excel. | • **Precisão:** Dados exatos ("12 minutos de contato visual") para dar segurança ao laudo.<br>• **Tempo:** Redução drástica do tempo de análise para ter qualidade de vida.<br>• **Simplicidade:** Uma ferramenta que não exija curso de TI para operar.<br>• **Validação:** Confirmar visualmente (gráficos) a evolução do paciente para mostrar aos pais. |

---

## 3. Contexto de Uso

* **Cenário:** Consultório clínico privado, ambiente silencioso e iluminado.
* **Equipamento:** Computador desktop na mesa de apoio e câmera em tripé.
* **Momento:** Pós-atendimento (assíncrono). O uso ocorre nos intervalos ou ao final do expediente, sem a presença do paciente.

---

## 4. Jornada do Usuário (Atual vs. Dor)

0. **Motivação**: Helena enxerga indícios para um diagnóstico de TEA em uma das crianças OU existe a requisição de um pai/mãe que está preocupado com o filho/a.
1.  **Sessão:** Helena grava a interação com a criança, tentando anotar pontos chave na prancheta (atenção dividida).
2.  **Extração:** Transfere o arquivo da câmera para o PC.
3.  **Análise Manual (Gargalo):** Abre o vídeo, assiste, pausa, anota o tempo, volta o vídeo. Repete isso por horas.
4.  **Impacto Pessoal:** Chega em casa tarde, cansada, e ainda precisa somar os tempos para o laudo. Perde o jantar com a família.
5.  **Laudo:** Entrega um relatório subjetivo, sentindo que poderia ser mais precisa.
6. **Pós-Laudo**: Tem a possibilidade de rodar novamente a solução e tirar suas conclusões novamente ou ir diretamente para um aprofundamento no diagnóstico.
---

### ⚠️ Entrega 4: Cenários de Análise (Problema)

**Status:** [Concluído]

---

#### Passo 1: Elementos Característicos do Cenário
* **Ambiente/Contexto:** Em casa, à noite, após uma semana intensa de atendimentos clínicos.
* **Atores:** Dra. Helena (neuropsicóloga infantil, exausta e sobrecarregada).
* **Objetivos:** Identificar traços de TEA em vídeos de sessões infantis para fundamentar prognósticos.
* **Planejamento:** Analisar horas de vídeo com atenção ininterrupta a detalhes sutis e consolidar os dados.
* **Ações:** Assistir, pausar e retroceder vídeos num player comum, fazendo anotações em planilhas.
* **Eventos:** O vídeo rola, o vídeo é pausado, o vídeo acaba, e parte para o próximo.
* **Avaliação:** Insegurança sobre a precisão da própria análise, frustração pela perda de tempo pessoal e preocupação com o atraso no retorno aos pais.

---

#### Passo 2: Narrativa Base
A Dra. Helena, neuropsicóloga infantil com quinze anos de experiência em desenvolvimento infantil e diagnóstico de TEA, encontra-se em sua casa, tarde da noite, após finalizar uma semana intensa de atendimentos clínicos. Tendo apenas o seu notebook e um player de vídeo comum à disposição, ela precisa analisar as gravações das sessões de três pacientes diferentes para fundamentar o seu prognóstico. Para isso, ela necessita identificar possíveis traços do Transtorno do Espectro Autista (TEA), como microexpressões sutis, padrões de atenção e movimentos atípicos das crianças. Embora sua vasta experiência clínica a capacite para reconhecer esses indicadores, o cansaço acumulado e a monotonia do trabalho repetitivo comprometem justamente essa habilidade perceptiva.

Durante a análises dos vídeos, Helena pausa os vídeos a partir de algum momento interessante, que julga ser digno de alguma anotação. Caso Helena não esteja satisfeita com sua própria análise, retoma o vídeo para uma revisão, e, caso tenha já concluído a análise, encerra e parte para o próximo vídeo.

Helena alcança esse objetivo executando o processo de forma totalmente manual, sem conhecer ou ter acesso a ferramentas alternativas de análise assistida por computador que poderiam auxiliá-la. As principais ações consistem em assistir, pausar e retroceder as mídias repetidas vezes, utilizando o mouse e teclado intensamente, enquanto anota cada detalhe observado e consolida essas informações em planilhas convencionais. Uma decisão equivocada nesse processo, como classificar incorretamente um comportamento como típico quando na verdade é um indicador de TEA, pode resultar em um prognóstico impreciso e atrasar a intervenção terapêutica precoce.

Como não há automação, a quantidade massiva de horas de vídeo exige um foco absoluto, e o principal problema que surge é uma fadiga visual e mental extrema após algumas horas de análise. Erros de observação podem ocorrer, como perder uma microexpressão ou confundir um comportamento atípico com um típico, e não há mecanismo de revisão ou checagem que permita identificar e corrigir esses equívocos. O acúmulo de horas de trabalho repetitivo sem pausas dispara um forte esgotamento e insegurança. Devido a isso, Helena termina a primeira análise avaliando negativamente a precisão do seu próprio trabalho, sem dispor de nenhum critério objetivo ou indicador que confirme se a análise foi concluída com a qualidade necessária. Resta-lhe apenas a própria percepção subjetiva, alimentada pelo medo de que detalhes cruciais tenham passado despercebidos aos seus olhos.

Além da insegurança profissional, a consequência direta dessa rotina é a frustração, pois o processo rouba o tempo valioso que ela gostaria de passar com sua família. Esse gargalo não afeta apenas a profissional, mas também atrasa o direcionamento diagnóstico para os pais dos pacientes, que dependem desse resultado e aguardam ansiosamente por respostas.

---

#### Passo 3: Questões de Refinamento (Extraídas de Barbosa e Silva, 2010)

**Ator(es)**
1. Quem pode alcançar o objetivo descrito no cenário?
2. Quais características da atora lhe auxiliam ou atrapalham em alcançar o objetivo?
3. Quem depende do resultado do objetivo?

**Ambiente**

4. Em que situações o cenário ocorre (quando, onde e por quê)?
5. Que dispositivos e outros recursos (inclusive tempo) estão disponíveis para o alcance do objetivo?

**Objetivo**

6. Por que os atores querem ou precisam alcançar esse objetivo?
7. De que informações ou conhecimento os atores precisam para realizar esse objetivo?

**Planejamento**

8. Como os atores alcançam o objetivo atualmente?
9. Quais são as estratégias alternativas para realizar o objetivo? Os atores as conhecem?
10. Que decisões os atores precisam tomar a cada momento? Quais as consequências de uma decisão errada?

**Ação**

11. Que ações realizam? Como essas ações estão relacionadas?
12. Como os atores as realizam fisicamente?
13. Quais informações são (ou deveriam ser) criadas, consumidas, manipuladas ou destruídas pela realização da ação?
14. Quais problemas ou dificuldades podem surgir ao realizá-la?
15. Quais erros podem ser cometidos ao realizá-la? Como podem ser desfeitos? Quais suas consequências?

**Evento**

16. Quais eventos disparam a necessidade de alcançar o objetivo?
17. Quais eventos são (ou deveriam ser) disparados pela conclusão desse objetivo?

**Avaliação**

18. Como os atores conseguem saber se o objetivo foi concluído e alcançado com sucesso?
19. Qual é o resultado do alcance do objetivo?
20. Quais consequências da atividade existem na rotina dos atores?

---

#### Passo 4: Cenário Final Referenciando as Perguntas (Mapeamento)

A Dra. Helena, neuropsicóloga infantil **[1]** com quinze anos de experiência em desenvolvimento infantil e diagnóstico de TEA, encontra-se em sua casa, tarde da noite, após finalizar uma semana intensa de atendimentos clínicos **[4]**. Tendo apenas o seu notebook e um player de vídeo comum à disposição **[5]**, ela precisa analisar as gravações das sessões de três pacientes diferentes para fundamentar o seu prognóstico **[6]**. Para isso, ela necessita identificar possíveis traços do Transtorno do Espectro Autista (TEA), como microexpressões sutis, padrões de atenção e movimentos atípicos das crianças **[7]**. Embora sua vasta experiência clínica a capacite para reconhecer esses indicadores, o cansaço acumulado e a monotonia do trabalho repetitivo comprometem justamente essa habilidade perceptiva **[2]**.

Durante a análises dos vídeos, Helena pausa os vídeos a partir de algum momento interessante, que julga ser digno de alguma anotação. **[16]** Caso Helena não esteja satisfeita com sua própria análise, retoma o vídeo para uma revisão, e, caso tenha já concluído a análise, encerra e parte para o próximo vídeo **[17]**

Helena alcança esse objetivo executando o processo de forma totalmente manual **[8]**, sem conhecer ou ter acesso a ferramentas alternativas de análise assistida por computador que poderiam auxiliá-la **[9]**. As principais ações consistem em assistir, pausar e retroceder as mídias repetidas vezes **[11]**, utilizando o mouse e teclado intensamente **[12]**, enquanto anota cada detalhe observado e consolida essas informações em planilhas convencionais **[13]**. Uma decisão equivocada nesse processo, como classificar incorretamente um comportamento como típico quando na verdade é um indicador de TEA, pode resultar em um prognóstico impreciso e atrasar a intervenção terapêutica precoce **[10]**.

Como não há automação, a quantidade massiva de horas de vídeo exige um foco absoluto, e o principal problema que surge é uma fadiga visual e mental extrema após algumas horas de análise **[14]**. Erros de observação podem ocorrer, como perder uma microexpressão ou confundir um comportamento atípico com um típico, e não há mecanismo de revisão ou checagem que permita identificar e corrigir esses equívocos **[15]**. O acúmulo de horas de trabalho repetitivo sem pausas dispara um forte esgotamento e insegurança, devido a isso, Helena termina a primeira análise avaliando negativamente a precisão do seu próprio trabalho, sem dispor de nenhum critério objetivo ou indicador que confirme se a análise foi concluída com a qualidade necessária **[18]**. Resta-lhe apenas a própria percepção subjetiva, alimentada pelo medo de que detalhes cruciais tenham passado despercebidos aos seus olhos **[19]**.

Além da insegurança profissional, a consequência direta dessa rotina é a frustração, pois o processo rouba o tempo valioso que ela gostaria de passar com sua família **[20]**. Esse gargalo não afeta apenas a profissional, mas também atrasa o direcionamento diagnóstico para os pais dos pacientes, que dependem desse resultado e aguardam ansiosamente por respostas **[3]**.

---

## 🛠️ Entrega 5: Análise de Tarefas
*Status: [Em andamento]*

### HTA (Hierarchical Task Analysis)
*Status: [Concluído]*

A seguir são apresentadas as Análises Hierárquicas de Tarefas das três tarefas mais importantes do sistema GAIA, modeladas conforme Barbosa e Silva (2010). Cada HTA é composto pelo diagrama hierárquico e pela tabela detalhada contendo Input, Feedback, Plano, Ação, Problemas e Recomendações.

---

### HTA 1: Submeter Vídeo ao Dataset de Treinamento (Módulo Admin)

![HTA 1 — Submeter Vídeo ao Dataset de Treinamento](./assets/hta1_admin_dataset.svg)

| Objetivos / Operações | Problemas e Recomendações |
| :--- | :--- |
| **0. Submeter vídeo ao dataset de treinamento** `1 > 2 > 3` | **Input:** Arquivo de vídeo de sessão infantil a ser incluído no dataset de treinamento da IA. **Feedback:** Vídeo aparece na lista do dashboard com status "Processado" e rótulo atribuído (Neurotípico ou TEA). **Plano:** Autenticar no sistema, depois cadastrar o novo vídeo, depois verificar o resultado do processamento. **Recomendação:** Permitir upload em lote para otimizar a curadoria de grandes volumes de vídeo. |
| **1. Autenticar no sistema** `1 > 2` | **Plano:** Inserir credenciais e depois confirmar login. |
| **1.1. Inserir credenciais** *(operação)* | **Ação:** Admin digita usuário e senha nos campos do formulário de login. |
| **1.2. Confirmar login** *(operação)* | **Ação:** Sistema valida as credenciais e redireciona para o dashboard. **Feedback:** Dashboard de vídeos do dataset é exibido. **Problema:** Credenciais inválidas não informam se o erro foi no usuário ou na senha. **Recomendação:** Exibir mensagem genérica de erro para segurança, mas com feedback visual claro de que a tentativa falhou. |
| **2. Cadastrar novo vídeo** `1 > 2 > 3` | **Plano:** Selecionar o arquivo de vídeo, depois classificar o rótulo, depois confirmar o upload. |
| **2.1. Selecionar arquivo de vídeo** *(operação)* | **Ação:** Admin clica no botão "+" e seleciona o arquivo de vídeo no explorador de arquivos. **Problema:** O sistema pode aceitar formatos de vídeo incompatíveis com o pipeline de processamento. **Recomendação:** Restringir formatos aceitos (.mp4, .avi) e exibir validação antes do upload. |
| **2.2. Classificar rótulo (Neurotípico / TEA)** *(operação)* | **Ação:** Admin seleciona a classificação do vídeo entre "Neurotípico" ou "TEA" antes de confirmar o envio. **Problema:** Erro de classificação compromete o treinamento do modelo (rótulo errado polui o dataset). **Recomendação:** Permitir edição posterior do rótulo e exigir confirmação explícita da classificação atribuída. |
| **2.3. Confirmar upload** *(operação)* | **Ação:** Admin clica em "Realizar Upload". O sistema inicia o envio e processamento do vídeo. **Feedback:** Barra de progresso durante o upload e mensagem de sucesso ao concluir. **Problema:** Em conexões lentas, o upload pode falhar sem feedback claro. **Recomendação:** Implementar retomada de upload interrompido e indicador de progresso com estimativa de tempo. |
| **3. Verificar resultado do processamento** *(operação)* | **Ação:** Admin visualiza o novo vídeo na lista do dashboard com seu rótulo e status de processamento. **Feedback:** Vídeo listado com status "Processado com sucesso" ou "Erro no processamento". **Problema:** Se o processamento falhar, o admin não sabe se deve tentar novamente ou se o vídeo é incompatível. **Recomendação:** Exibir mensagem de erro detalhada com orientação sobre a causa e próximos passos. |

---

### HTA 2: Submeter Vídeo para Prognóstico Clínico (Módulo Especialista)

![HTA 2 — Submeter Vídeo para Prognóstico Clínico](./assets/hta2_especialista_prognostico.svg)

| Objetivos / Operações | Problemas e Recomendações |
| :--- | :--- |
| **0. Submeter vídeo para prognóstico clínico** `1 > 2 > 3` | **Input:** Arquivo de vídeo de sessão gravada com paciente infantil. **Feedback:** Dashboard exibe o vídeo processado com indicador de risco TEA e insights comportamentais detalhados. **Plano:** Autenticar no sistema, depois enviar o vídeo para análise, depois analisar o resultado do prognóstico. **Recomendação:** Notificar o especialista (e-mail ou push) quando o processamento assíncrono for concluído. |
| **1. Autenticar no sistema** `1 > 2` | **Plano:** Inserir credenciais e depois confirmar login. |
| **1.1. Inserir credenciais** *(operação)* | **Ação:** Especialista digita usuário e senha nos campos do formulário de login. |
| **1.2. Confirmar login** *(operação)* | **Ação:** Sistema valida as credenciais e redireciona para o dashboard clínico. **Feedback:** Dashboard de vídeos do especialista é exibido. |
| **2. Enviar vídeo para análise** `1 > 2` | **Plano:** Selecionar o arquivo de vídeo e depois confirmar upload. |
| **2.1. Selecionar arquivo de vídeo** *(operação)* | **Ação:** Especialista clica no botão "+" e seleciona o arquivo de vídeo da sessão no explorador de arquivos. **Problema:** Vídeos de sessões longas podem ser muito pesados, tornando o upload demorado. **Recomendação:** Exibir limite de tamanho antes da seleção e sugerir compressão quando aplicável. |
| **2.2. Confirmar upload** *(operação)* | **Ação:** Especialista clica em "Realizar Upload". O sistema inicia o envio e enfileira o vídeo para processamento pela IA. **Feedback:** Barra de progresso e mensagem informando que o processamento está em andamento. **Problema:** O tempo de processamento da IA pode ser longo e o especialista não sabe quanto tempo falta. **Recomendação:** Exibir estimativa de tempo de processamento e permitir que o especialista continue navegando enquanto aguarda. |
| **3. Analisar resultado do prognóstico** `1 + 2` | **Plano:** Visualizar o indicador de risco TEA e, simultaneamente, visualizar os insights comportamentais. |
| **3.1. Visualizar indicador de risco TEA** *(operação)* | **Ação:** Especialista lê o percentual de probabilidade de risco de TEA gerado pela IA. **Feedback:** Indicador numérico e visual (ex.: gauge ou barra colorida) exibido na tela de resultado. **Problema:** O especialista pode interpretar o indicador como diagnóstico definitivo e não como apoio à decisão. **Recomendação:** Exibir disclaimer explícito de que o indicador é um suporte ao prognóstico, não um diagnóstico. |
| **3.2. Visualizar insights comportamentais** *(operação)* | **Ação:** Especialista analisa gráficos e métricas detalhadas: porcentagem de tempo de olhar mútuo ("Warm"), análise postural, padrões de atenção e outros indicadores. **Feedback:** Dashboard com gráficos interativos, timeline comportamental e destaques visuais sobre o vídeo. **Problema:** Excesso de dados pode sobrecarregar o especialista, dificultando a interpretação. **Recomendação:** Apresentar um resumo executivo com os achados mais relevantes e permitir drill-down nos detalhes sob demanda. |

---

### HTA 3: Consultar Análise de Vídeo Já Processado (Módulo Especialista)

![HTA 3 — Consultar Análise de Vídeo Já Processado](./assets/hta3_especialista_consulta.svg)

| Objetivos / Operações | Problemas e Recomendações |
| :--- | :--- |
| **0. Consultar análise de vídeo já processado** `1 > 2 > 3` | **Input:** Intenção de revisar dados de um vídeo previamente analisado pela IA. **Feedback:** Dados completos do vídeo selecionado são exibidos na interface. **Plano:** Autenticar no sistema, depois selecionar o vídeo no dashboard, depois analisar os dados do vídeo. |
| **1. Autenticar no sistema** `1 > 2` | **Plano:** Inserir credenciais e depois confirmar login. |
| **1.1. Inserir credenciais** *(operação)* | **Ação:** Especialista digita usuário e senha nos campos do formulário de login. |
| **1.2. Confirmar login** *(operação)* | **Ação:** Sistema valida as credenciais e redireciona para o dashboard clínico. **Feedback:** Dashboard de vídeos do especialista é exibido com a lista de vídeos já processados. |
| **2. Selecionar vídeo no dashboard** *(operação)* | **Ação:** Especialista localiza o vídeo desejado na lista do dashboard e clica sobre ele. **Problema:** Com muitos vídeos cadastrados, localizar um vídeo específico pode ser difícil. **Recomendação:** Implementar busca por nome do paciente, data da sessão ou filtros por status/resultado. |
| **3. Analisar dados do vídeo** `1 / 2` | **Plano:** Visualizar métricas e insights OU reproduzir o vídeo com anotações da IA (dependendo da necessidade do momento). |
| **3.1. Visualizar métricas e insights** *(operação)* | **Ação:** Especialista visualiza o dashboard de dados do vídeo: indicador de risco, gráficos de olhar mútuo, postura, padrões de atenção e demais insights. **Feedback:** Dashboard completo com todas as métricas computadas pela IA. **Problema:** Se o especialista quiser comparar este vídeo com sessões anteriores do mesmo paciente, não há mecanismo de comparação. **Recomendação:** Oferecer funcionalidade de comparação longitudinal entre sessões do mesmo paciente para acompanhar evolução. |
| **3.2. Reproduzir vídeo com anotações da IA** *(operação)* | **Ação:** Especialista reproduz o vídeo processado com sobreposições visuais (bounding boxes, marcações de atenção, face mesh). **Feedback:** Player de vídeo exibe as anotações da IA sincronizadas com a reprodução. **Problema:** Vídeos com muitas anotações podem ficar visualmente poluídos, dificultando a observação do comportamento natural da criança. **Recomendação:** Permitir que o especialista ative/desative camadas de anotação individualmente (ex.: mostrar apenas face mesh, ou apenas marcações de atenção). |

---

### 2) GOMS (Goals, Operators, Methods, Selection Rules)

A seguir são apresentados os modelos GOMS das tarefas principais do sistema GAIA, seguindo a notação de Barbosa e Silva (2010). Para cada tarefa, é apresentada uma versão resumida e uma versão detalhada com operadores primitivos, além da análise KLM (Keystroke-Level Model) para comparação de eficiência.

---

#### GOMS — Tarefa 1: Submeter Vídeo para Prognóstico Clínico (Módulo Especialista)

**Versão Resumida:**

```
GOAL 0: obter prognóstico de TEA para paciente a partir de vídeo de sessão
    GOAL 1: acessar o sistema
        METHOD 1.A: login com credenciais salvas no navegador
            (SEL. RULE: o navegador possui as credenciais salvas e o usuário aceita o preenchimento automático)
        METHOD 1.B: login com digitação manual
            (SEL. RULE: primeiro acesso, ou credenciais não salvas, ou outro computador)
    GOAL 2: cadastrar novo vídeo para análise
        METHOD 2.A: upload por seleção no explorador de arquivos
            (SEL. RULE: o especialista sabe a localização do arquivo no computador)
        METHOD 2.B: upload por arrastar e soltar (drag and drop)
            (SEL. RULE: a janela do explorador de arquivos já está aberta ao lado do navegador)
    GOAL 3: analisar resultado do prognóstico
        GOAL 3.1: interpretar indicador de risco TEA
        GOAL 3.2: interpretar insights comportamentais
```

**Versão Detalhada:**

```
GOAL 0: obter prognóstico de TEA para paciente a partir de vídeo de sessão

    GOAL 1: acessar o sistema

        METHOD 1.A: login com credenciais salvas no navegador
        (SEL. RULE: o navegador possui as credenciais salvas e o usuário aceita o preenchimento automático)
            OP. 1.A.1: deslocar o cursor do mouse para o campo de usuário
            OP. 1.A.2: clicar com o botão esquerdo do mouse para ativar o preenchimento automático
            OP. 1.A.3: selecionar a conta desejada na lista suspensa do navegador
            OP. 1.A.4: deslocar o cursor do mouse para o botão "Entrar"
            OP. 1.A.5: clicar com o botão esquerdo do mouse
            OP. 1.A.6: verificar se o dashboard foi carregado corretamente

        METHOD 1.B: login com digitação manual
        (SEL. RULE: primeiro acesso, ou credenciais não salvas, ou outro computador)
            OP. 1.B.1: deslocar o cursor do mouse para o campo de usuário
            OP. 1.B.2: clicar com o botão esquerdo do mouse
            OP. 1.B.3: digitar o nome de usuário
            OP. 1.B.4: pressionar a tecla Tab para ir ao campo de senha
            OP. 1.B.5: digitar a senha
            OP. 1.B.6: deslocar o cursor do mouse para o botão "Entrar"
            OP. 1.B.7: clicar com o botão esquerdo do mouse
            OP. 1.B.8: verificar se o dashboard foi carregado corretamente

    GOAL 2: cadastrar novo vídeo para análise

        METHOD 2.A: upload por seleção no explorador de arquivos
        (SEL. RULE: o especialista sabe a localização do arquivo no computador)
            OP. 2.A.1: deslocar o cursor do mouse para o botão "+"
            OP. 2.A.2: clicar com o botão esquerdo do mouse
            OP. 2.A.3: aguardar abertura do explorador de arquivos do sistema operacional
            OP. 2.A.4: navegar até a pasta onde o vídeo está salvo
            OP. 2.A.5: selecionar o arquivo de vídeo desejado
            OP. 2.A.6: clicar no botão "Abrir" do explorador de arquivos
            OP. 2.A.7: verificar se o nome do arquivo apareceu na interface
            OP. 2.A.8: deslocar o cursor do mouse para o botão "Realizar Upload"
            OP. 2.A.9: clicar com o botão esquerdo do mouse
            OP. 2.A.10: aguardar processamento pela IA

        METHOD 2.B: upload por arrastar e soltar (drag and drop)
        (SEL. RULE: a janela do explorador de arquivos já está aberta ao lado do navegador)
            OP. 2.B.1: localizar o arquivo de vídeo na janela do explorador de arquivos
            OP. 2.B.2: pressionar o botão esquerdo do mouse sobre o arquivo
            OP. 2.B.3: arrastar o arquivo até a zona de upload na interface do GAIA
            OP. 2.B.4: soltar o botão esquerdo do mouse
            OP. 2.B.5: verificar se o nome do arquivo apareceu na interface
            OP. 2.B.6: deslocar o cursor do mouse para o botão "Realizar Upload"
            OP. 2.B.7: clicar com o botão esquerdo do mouse
            OP. 2.B.8: aguardar processamento pela IA

    GOAL 3: analisar resultado do prognóstico

        GOAL 3.1: interpretar indicador de risco TEA
            OP. 3.1.1: examinar o indicador percentual de probabilidade de risco de TEA
            OP. 3.1.2: examinar a escala visual (gauge ou barra colorida) associada ao indicador

        GOAL 3.2: interpretar insights comportamentais
            OP. 3.2.1: examinar gráfico de porcentagem de tempo de olhar mútuo ("Warm")
            OP. 3.2.2: examinar dados de análise postural
            OP. 3.2.3: examinar demais indicadores de padrões de atenção
            OP. 3.2.4: verificar resumo executivo dos achados mais relevantes
```

---

#### GOMS-KLM — Comparação de Métodos de Upload

Análise comparativa do tempo estimado para o upload de vídeo utilizando os dois métodos disponíveis, conforme o modelo KLM (Keystroke-Level Model).

**METHOD 2.A — Upload por seleção no explorador de arquivos:**

| Operador | Descrição | Tempo (s) |
| :--- | :--- | :--- |
| M | Preparação mental (decidir fazer upload) | 1,20 |
| P | Levar o cursor até o botão "+" | 1,10 |
| B | Pressionar o botão do mouse | 0,10 |
| B | Soltar o botão do mouse | 0,10 |
| R | Aguardar abertura do explorador de arquivos | 1,00 |
| M | Preparação mental (localizar a pasta) | 1,20 |
| P | Navegar e selecionar o arquivo | 1,10 |
| B | Pressionar o botão do mouse (selecionar) | 0,10 |
| B | Soltar o botão do mouse | 0,10 |
| P | Levar o cursor até "Abrir" | 1,10 |
| B | Pressionar o botão do mouse | 0,10 |
| B | Soltar o botão do mouse | 0,10 |
| M | Preparação mental (confirmar upload) | 1,20 |
| P | Levar o cursor até "Realizar Upload" | 1,10 |
| B | Pressionar o botão do mouse | 0,10 |
| B | Soltar o botão do mouse | 0,10 |
| | **TOTAL** | **9,80** |

**METHOD 2.B — Upload por arrastar e soltar (drag and drop):**

| Operador | Descrição | Tempo (s) |
| :--- | :--- | :--- |
| M | Preparação mental (decidir fazer upload) | 1,20 |
| P | Levar o cursor até o arquivo no explorador | 1,10 |
| B | Pressionar o botão do mouse (segurar) | 0,10 |
| P | Arrastar até a zona de upload do GAIA | 1,10 |
| B | Soltar o botão do mouse | 0,10 |
| M | Preparação mental (confirmar upload) | 1,20 |
| P | Levar o cursor até "Realizar Upload" | 1,10 |
| B | Pressionar o botão do mouse | 0,10 |
| B | Soltar o botão do mouse | 0,10 |
| | **TOTAL** | **6,10** |

**Conclusão KLM:** O método de drag and drop (6,10s) é **37,8% mais rápido** que o método de seleção via explorador (9,80s), pois elimina a abertura do explorador de arquivos e a navegação de pastas. No entanto, a regra de seleção indica que ele só é viável quando a janela do explorador já está aberta ao lado do navegador.

---

#### GOMS — Tarefa 2: Consultar Análise de Vídeo Já Processado (Módulo Especialista)

**Versão Resumida:**

```
GOAL 0: consultar análise de vídeo já processado para fundamentar laudo
    GOAL 1: acessar o sistema
        METHOD 1.A: login com credenciais salvas no navegador
            (SEL. RULE: o navegador possui as credenciais salvas)
        METHOD 1.B: login com digitação manual
            (SEL. RULE: credenciais não salvas ou outro computador)
    GOAL 2: localizar o vídeo desejado
        METHOD 2.A: buscar pelo nome do paciente ou data
            (SEL. RULE: o especialista sabe o nome do paciente ou a data da sessão)
        METHOD 2.B: navegar pela lista do dashboard
            (SEL. RULE: o vídeo foi processado recentemente e deve estar no topo da lista)
    GOAL 3: analisar dados do vídeo
        METHOD 3.A: visualizar métricas e insights no dashboard
            (SEL. RULE: o especialista precisa de dados quantitativos para o laudo)
        METHOD 3.B: reproduzir vídeo com anotações da IA
            (SEL. RULE: o especialista precisa revisar visualmente o comportamento da criança)
```

**Versão Detalhada:**

```
GOAL 0: consultar análise de vídeo já processado para fundamentar laudo

    GOAL 1: acessar o sistema
        (métodos 1.A e 1.B idênticos à Tarefa 1)

    GOAL 2: localizar o vídeo desejado

        METHOD 2.A: buscar pelo nome do paciente ou data
        (SEL. RULE: o especialista sabe o nome do paciente ou a data da sessão)
            OP. 2.A.1: deslocar o cursor do mouse para o campo de busca
            OP. 2.A.2: clicar com o botão esquerdo do mouse
            OP. 2.A.3: digitar o nome do paciente ou data da sessão
            OP. 2.A.4: pressionar Enter ou clicar no ícone de busca
            OP. 2.A.5: verificar resultados retornados
            OP. 2.A.6: clicar sobre o vídeo desejado na lista de resultados

        METHOD 2.B: navegar pela lista do dashboard
        (SEL. RULE: o vídeo foi processado recentemente e deve estar no topo da lista)
            OP. 2.B.1: examinar a lista de vídeos no dashboard
            OP. 2.B.2: deslocar o cursor do mouse para o vídeo desejado
            OP. 2.B.3: clicar com o botão esquerdo do mouse sobre o vídeo

    GOAL 3: analisar dados do vídeo

        METHOD 3.A: visualizar métricas e insights no dashboard
        (SEL. RULE: o especialista precisa de dados quantitativos para o laudo)
            OP. 3.A.1: examinar indicador percentual de risco TEA
            OP. 3.A.2: examinar gráfico de tempo de olhar mútuo ("Warm")
            OP. 3.A.3: examinar dados de análise postural
            OP. 3.A.4: examinar padrões de atenção e demais insights
            OP. 3.A.5: examinar resumo executivo dos achados

        METHOD 3.B: reproduzir vídeo com anotações da IA
        (SEL. RULE: o especialista precisa revisar visualmente o comportamento da criança)
            OP. 3.B.1: deslocar o cursor do mouse para o botão "Play" do player de vídeo
            OP. 3.B.2: clicar com o botão esquerdo do mouse
            OP. 3.B.3: observar o vídeo com as sobreposições da IA (bounding boxes, face mesh)
            OP. 3.B.4: pausar e retroceder conforme necessário para análise detalhada
            OP. 3.B.5: verificar se as anotações da IA correspondem à percepção clínica
```

---

### 3) CTT (ConcurTaskTrees)

A seguir são apresentados os modelos CTT das tarefas do GAIA utilizando a notação de Barbosa e Silva (2010), com os 4 tipos de tarefa e as relações temporais entre elas.

---

#### CTT — Tarefa 1: Submeter Vídeo para Prognóstico Clínico

![CTT 1 — Submeter Vídeo para Prognóstico Clínico](./assets/ctt1_prognostico.svg)

**Explicação das relações utilizadas:**

- **Identificar necessidade de análise `>>` Submeter e processar vídeo:** ativação — a especialista primeiro identifica a necessidade clínica de analisar o paciente (tarefa do usuário, fora do sistema), e só então inicia a interação com o GAIA.
- **Autenticar `>>` Selecionar arquivo:** ativação — o upload só pode ser feito após a autenticação.
- **Selecionar arquivo `[]>>` Confirmar upload:** ativação com passagem de informação — o arquivo selecionado é passado para a etapa de confirmação.
- **Confirmar upload `[]>>` Processar vídeo:** ativação com passagem de informação — o vídeo enviado é passado ao pipeline de IA para processamento.
- **Submeter e processar `[]>>` Analisar resultado:** ativação com passagem de informação — os dados processados pela IA são passados para a tela de resultado.
- **Visualizar indicador `|||` Visualizar insights:** concorrência — o especialista pode examinar o indicador de risco e os gráficos de insights em qualquer ordem ou simultaneamente na mesma tela.
- **Analisar resultado `[]>>` Interpretar resultados para o laudo:** ativação com passagem de informação — após visualizar os dados do sistema, a especialista realiza a interpretação clínica (tarefa do usuário, fora do sistema) para incorporar os achados ao laudo.

---

#### CTT — Tarefa 2: Consultar Análise de Vídeo Já Processado

![CTT 2 — Consultar Análise de Vídeo Já Processado](./assets/ctt2_consulta.svg)

**Explicação das relações utilizadas:**

- **Decidir consultar dados para o laudo `>>` Acessar e localizar vídeo:** ativação — a especialista primeiro decide que precisa revisar dados de um caso (tarefa do usuário, fora do sistema), e só então acessa o GAIA.
- **Autenticar `>>` Localizar vídeo:** ativação — a navegação só ocorre após autenticação.
- **Buscar por nome/data `[]` Navegar pela lista:** escolha — o especialista utiliza a busca OU a navegação manual; uma vez iniciado um método, o outro fica desabilitado naquela ação.
- **Acessar e localizar `[]>>` Analisar dados:** ativação com passagem de informação — o vídeo selecionado é passado para a tela de análise detalhada.
- **Visualizar métricas `|=|` Reproduzir vídeo:** independência — o especialista pode realizar as duas atividades em qualquer ordem, mas quando inicia uma, precisa concluí-la antes de focar na outra.
- **Analisar dados `[]>>` Consolidar percepção clínica:** ativação com passagem de informação — após interagir com os dados do sistema, a especialista consolida sua percepção clínica sobre o caso (tarefa do usuário, fora do sistema) para embasar o laudo.

---

## 📝 Entrega 6: Prototipação de Baixa Fidelidade

### Tela 01 — Login
![Tela Login](./assets/tela01_login.png)

### Tela 02 — Dashboard Admin
![Dashboard Admin](./assets/tela02_dashboard_admin.png)

### Tela 03 — Upload: Seleção de Arquivo
![Upload Seleção](./assets/tela03_upload_selecao.png)

### Tela 04 — Upload: Classificação
![Upload Classificar](./assets/tela04_upload_classificar.png)

### Tela 05 — Upload: Confirmação
![Upload Confirmar](./assets/tela05_upload_confirmar.png)

### Tela 06 — Dashboard Especialista
![Dashboard Especialista](./assets/tela06_dashboard_especialista.png)

### Tela 07 — Upload Especialista
![Upload Especialista](./assets/tela07_upload_especialista.png)

### Tela 08 — Resultado do Prognóstico
![Resultado Prognóstico](./assets/tela08_resultado_prognostico.png)

---

## 📋 Entrega 7: Requisitos e Ética
*Status: Concluído*

---

### 1) Que Dados Coletar?

Seguindo Barbosa e Silva (2010), os dados a serem coletados sobre os usuários do sistema GAIA se organizam em cinco eixos:

#### 1.1 Dados sobre o próprio usuário
Buscamos entender o perfil demográfico e de formação do especialista que utilizará o sistema:
- Faixa etária e gênero
- Grau de instrução e área de formação (Psicologia, Neuropsicologia, Fonoaudiologia, etc.)
- Tempo de atuação na área clínica com crianças com TEA
- Contexto de trabalho (clínica particular, hospital, escola especializada, pesquisa)

#### 1.2 Dados sobre sua relação com tecnologia
Compreender o nível de familiaridade tecnológica é essencial para calibrar a complexidade da interface:
- Nível de experiência com computadores e softwares clínicos
- Ferramentas computacionais já utilizadas na rotina profissional (prontuários eletrônicos, planilhas, plataformas de teleatendimento)
- Experiência prévia com sistemas de análise assistida por IA ou videoconferência clínica
- Dispositivos habitualmente utilizados no trabalho (desktop, notebook, tablet)

#### 1.3 Dados sobre seu conhecimento do domínio
- Nível de familiaridade com critérios diagnósticos de TEA (DSM-5, CID-11)
- Conhecimento sobre métricas comportamentais observáveis em sessão (contato visual, postura, proximidade física)
- Experiência com análise de vídeos de sessões terapêuticas

#### 1.4 Dados sobre suas tarefas
- Quais são as principais atividades realizadas na avaliação de TEA atualmente?
- Como é feita hoje a análise de sessões (manual, com software, com apoio de equipe)?
- Qual a frequência e duração média das sessões analisadas?
- Quais os maiores gargalos e dificuldades do processo atual?
- Qual a gravidade dos erros de classificação comportamental para o diagnóstico?

#### 1.5 Dados sobre suas motivações e valores
- O especialista estaria disposto a adotar uma ferramenta de auxílio computacional ao diagnóstico?
- Qual o nível de confiança depositado em sistemas de IA para apoio clínico?
- O quanto valoriza objetividade e rastreabilidade nas avaliações?
- Prefere aprender novas ferramentas por conta própria, ou necessita de treinamento guiado?

---

### 2) De Quem Coletar?

Conforme Barbosa e Silva (2010), os dados devem ser coletados dos **usuários finais** e **stakeholders** do sistema.

Para o GAIA, os participantes-alvo são:

| Perfil | Justificativa |
| :--- | :--- |
| **Neuropsicólogos e psicólogos clínicos** com experiência em TEA | Usuário primário do sistema — quem interpreta os resultados e toma decisões diagnósticas |
| **Terapeutas ocupacionais e fonoaudiólogos** que atuam com TEA | Usuários secundários — podem usar o sistema para acompanhamento de evolução |
| **Pesquisadores** da área de comportamento infantil e neurodesenvolvimento | Stakeholders — interessados nos dados gerados pelo pipeline para fins científicos |

**Questões norteadoras da seleção (Barbosa e Silva, 2010):**
- *Quem utilizará o sistema?* → Especialistas clínicos com formação em saúde mental infantil
- *Quem será afetado por ele?* → Os próprios especialistas, as crianças avaliadas e seus responsáveis
- *Quem decide os objetivos que o sistema deve apoiar?* → O orientador clínico e os pesquisadores da UNSW/FEI
- *Quem definiu os processos a serem apoiados?* → A equipe do PCRC/UNSW, que conduziu as sessões originais

---

### 2) Aspectos Éticos

A pesquisa com usuários especialistas envolve coleta de dados de pessoas direta ou indiretamente, devendo seguir os princípios da **Resolução nº 196/96 do Conselho Nacional de Saúde**, conforme recomendado por Barbosa e Silva (2010):

| Princípio | Aplicação no GAIA |
| :--- | :--- |
| **Não maleficência** | O questionário não expõe os participantes a riscos físicos, emocionais ou profissionais. As perguntas são de caráter técnico-profissional, sem coleta de dados clínicos dos pacientes atendidos pelos participantes. |
| **Justiça e equidade** | A pesquisa beneficia diretamente os próprios especialistas participantes, ao contribuir para o desenvolvimento de uma ferramenta que aliviará sua carga de trabalho. Não há ônus desproporcional para grupos vulneráveis. |
| **Autonomia** | A participação é voluntária. Os respondentes são informados dos objetivos da pesquisa antes de iniciarem o questionário e podem interromper sua participação a qualquer momento, sem qualquer consequência. |
| **Beneficência** | Os resultados da coleta serão usados exclusivamente para aprimorar a usabilidade do sistema GAIA, gerando benefícios diretos à prática clínica dos participantes e indiretos às crianças atendidas. |

Na prática, o questionário será aplicado com as seguintes garantias:
- Os objetivos da pesquisa são explicados na introdução do formulário
- Nenhum dado de identificação pessoal será divulgado publicamente — os dados serão apresentados de forma anonimizada
- Nenhuma informação sobre pacientes atendidos pelos participantes será solicitada
- A participação é inteiramente voluntária e o respondente pode encerrar a qualquer momento

---

### 3) Ferramenta de Coleta de Dados

**Instrumento escolhido:** Questionário online (Google Forms)

**Justificativa da escolha:** O questionário permite coletar dados de múltiplos especialistas de forma rápida, padronizada e assíncrona — sem exigir deslocamento ou agendamento —, sendo adequado para o perfil do público-alvo (profissionais de saúde com agenda restrita). Conforme Barbosa e Silva (2010), o questionário é um meio rápido e eficaz para obtenção de dados em maior escala, sendo especialmente indicado quando o pesquisador já tem clareza sobre quais informações precisa coletar.

**Como aplicar:** O link do formulário será compartilhado diretamente com os especialistas via contato pessoal do pesquisador (WhatsApp e e-mail profissional). O formulário será precedido por uma breve apresentação do projeto e das garantias éticas, e estimado em 8 a 12 minutos de preenchimento.

---

#### Roteiro do Questionário — GAIA: Sistema de Análise de Interação Terapêutica

> *Introdução exibida ao respondente:*
> Este questionário faz parte de uma pesquisa de Trabalho de Conclusão de Curso (TCC) do Centro Universitário FEI, cujo objetivo é levantar requisitos de usabilidade para o sistema GAIA — uma ferramenta de apoio computacional à análise de sessões de interação terapêutica com crianças com suspeita de TEA. Sua participação é voluntária e anônima. Nenhuma informação sobre seus pacientes será solicitada. Tempo estimado: 10 minutos.

---

**Bloco 1 — Perfil do Respondente**
*(dados sobre o próprio usuário — Barbosa e Silva, 2010, eixo 1)*

**Q1.** Qual é a sua faixa etária?
- ( ) Abaixo de 25 anos
- ( ) 25–34 anos
- ( ) 35–44 anos
- ( ) 45–54 anos
- ( ) 55 anos ou mais

**Q2.** Qual é a sua área de formação principal? *(escolha até 2 opções)*
- [ ] Psicologia
- [ ] Neuropsicologia
- [ ] Fonoaudiologia
- [ ] Terapia Ocupacional
- [ ] Pedagogia / Educação Especial
- [ ] Outra: ___________

**Q3.** Há quanto tempo você atua clinicamente com crianças com TEA ou suspeita de TEA?
- ( ) Menos de 1 ano
- ( ) 1–3 anos
- ( ) 4–7 anos
- ( ) 8–15 anos
- ( ) Mais de 15 anos

**Q4.** Em qual contexto você exerce sua prática profissional? *(escolha até 2 opções)*
- [ ] Clínica particular
- [ ] Hospital ou UBS
- [ ] Escola ou centro de educação especial
- [ ] Pesquisa acadêmica
- [ ] Outro: ___________

---

**Bloco 2 — Relação com Tecnologia**
*(dados sobre relação com tecnologia — Barbosa e Silva, 2010, eixo 2)*

**Q5.** Como você avalia seu nível geral de experiência com tecnologia e computadores?
- ( ) Básico — uso e-mail e navegação web
- ( ) Intermediário — uso planilhas, prontuários eletrônicos, videoconferência
- ( ) Avançado — uso softwares especializados, analiso dados, configuro sistemas
- ( ) Especialista — tenho formação ou experiência técnica em TI

**Q6.** Quais das seguintes ferramentas digitais você já utilizou na sua prática profissional? *(marque todas que se aplicam)*
- [ ] Prontuário eletrônico (ex.: iClinic, ProntMed)
- [ ] Plataformas de teleatendimento (ex.: Zoom, Google Meet)
- [ ] Planilhas para registro de evolução (ex.: Excel, Google Sheets)
- [ ] Software de análise de vídeo (ex.: ELAN, Observer XT)
- [ ] Ferramentas com inteligência artificial para apoio clínico
- [ ] Nenhuma das anteriores

**Q7.** Você já utilizou algum sistema ou ferramenta que usa Inteligência Artificial para apoiar decisões clínicas?
- ( ) Sim, uso regularmente
- ( ) Sim, já experimentei pontualmente
- ( ) Não, mas tenho interesse
- ( ) Não, e não tenho interesse no momento

---

**Bloco 3 — Conhecimento do Domínio e Tarefas Atuais**
*(dados sobre domínio e tarefas — Barbosa e Silva, 2010, eixos 3 e 4)*

**Q8.** Com que frequência você analisa vídeos de sessões terapêuticas como parte do seu processo de avaliação de TEA?
- ( ) Nunca
- ( ) Raramente (menos de 1x por mês)
- ( ) Ocasionalmente (1–3x por mês)
- ( ) Frequentemente (1x por semana ou mais)

**Q9.** Quando analisa vídeos de sessões, como você costuma fazer isso atualmente? *(marque todas que se aplicam)*
- [ ] Assisto ao vídeo integralmente e anoto observações manualmente
- [ ] Assisto em partes, pausando e retrocedendo conforme necessário
- [ ] Utilizo algum software específico de anotação de comportamento
- [ ] Faço análise em equipe com outros profissionais
- [ ] Não analiso vídeos atualmente

**Q10.** Quais comportamentos você mais busca observar e registrar ao analisar vídeos de sessões? *(marque até 3 opções)*
- [ ] Contato visual e direção do olhar
- [ ] Expressão facial e emoções
- [ ] Postura e movimentação corporal
- [ ] Distância interpessoal (criança–guardião)
- [ ] Resposta a estímulos verbais
- [ ] Iniciativa de interação
- [ ] Outro: ___________

**Q11.** Quanto tempo, em média, você gasta analisando manualmente uma sessão de 30 minutos?
- ( ) Menos de 30 minutos
- ( ) 30 min – 1 hora
- ( ) 1–2 horas
- ( ) Mais de 2 horas

**Q12.** Quais são as maiores dificuldades do seu processo atual de análise de sessões? *(pergunta aberta)*

> _____________________________________________________________

---

**Bloco 4 — Motivações, Valores e Expectativas sobre o GAIA**
*(dados sobre motivações e valores — Barbosa e Silva, 2010, eixo 5)*

**Q13.** Para cada afirmação abaixo, indique seu grau de concordância: *(Escala de Likert: 1 = Discordo totalmente → 5 = Concordo plenamente)*

| Afirmação | 1 | 2 | 3 | 4 | 5 |
| :--- | :-: | :-: | :-: | :-: | :-: |
| A análise manual de vídeos de sessões é um processo desgastante | ○ | ○ | ○ | ○ | ○ |
| Métricas objetivas (ex.: % de contato visual) agregariam valor ao meu laudo | ○ | ○ | ○ | ○ | ○ |
| Confiaria em dados gerados por IA como *apoio* (não substituição) ao diagnóstico | ○ | ○ | ○ | ○ | ○ |
| Estaria disposto(a) a aprender a usar um novo sistema se ele reduzisse meu tempo de análise | ○ | ○ | ○ | ○ | ○ |
| A privacidade dos vídeos de sessão é um fator crítico para eu adotar qualquer ferramenta | ○ | ○ | ○ | ○ | ○ |

**Q14.** Como você avalia as características abaixo em um sistema de análise de sessões? *(Escala de diferenciais semânticos)*

| | 1 | 2 | 3 | 4 | 5 | |
| ---: | :-: | :-: | :-: | :-: | :-: | :--- |
| Essencial | ○ | ○ | ○ | ○ | ○ | Dispensável *(interface simples e intuitiva)* |
| Essencial | ○ | ○ | ○ | ○ | ○ | Dispensável *(processamento automático em segundo plano)* |
| Essencial | ○ | ○ | ○ | ○ | ○ | Dispensável *(exportação de relatório em PDF)* |
| Essencial | ○ | ○ | ○ | ○ | ○ | Dispensável *(armazenamento local dos vídeos, sem nuvem)* |

**Q15.** Que funcionalidade você considera mais importante em um sistema como o GAIA? *(pergunta aberta)*

> _____________________________________________________________

**Q16.** Você teria alguma preocupação em adotar um sistema de IA para apoio ao diagnóstico de TEA? Se sim, qual?  *(pergunta aberta)*

> _____________________________________________________________

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. Interação Humano-Computador. Elsevier, 2010. Editado por Plinio Aquino.*

---

## 🔄 Entrega 8: Engenharia de Usabilidade
*Status: Concluído*

> Baseado no Ciclo da Engenharia de Usabilidade de Mayhew (Barbosa e Silva, 2010): análise das capacidades e restrições da plataforma, análise de princípios gerais para o projeto e especificação dos objetivos de usabilidade.

---

### 1. Características da Plataforma

#### 1.1 Descrição de Software e Hardware

| Característica | Descrição |
| :--- | :--- |
| **Tipo de sistema** | Aplicação desktop local (não requer conexão com internet para processamento) |
| **Linguagem e stack principal** | Python 3.10+, com bibliotecas PyTorch, Ultralytics (YOLOv8), MediaPipe, OpenCV e BoTSORT |
| **Interface do usuário** | Aplicação web local servida via navegador (localhost), desenvolvida com HTML, CSS e JavaScript |
| **Sistema operacional** | Windows 10/11 (64-bit) — ambiente primário de uso clínico |
| **Hardware mínimo recomendado** | CPU: Intel Core i7 (8ª geração ou superior) / AMD Ryzen 7; RAM: 16 GB; GPU: NVIDIA com suporte a CUDA (mínimo 6 GB VRAM); Armazenamento: 50 GB livres para vídeos e modelos |
| **Hardware do ambiente de desenvolvimento** | NVIDIA RTX 5060, AMD Ryzen 7 5700X, 32 GB RAM |
| **Câmera / entrada de vídeo** | Não requer câmera — o sistema processa arquivos de vídeo pré-gravados (.mp4, .avi, .mov) |
| **Resolução de vídeo suportada** | 1280×720 (padrão do dataset UNSW); compatível com resoluções superiores |

---

#### 1.2 Capacidades da Plataforma

| Capacidade | Justificativa |
| :--- | :--- |
| **Detecção e rastreamento de pessoas em vídeo** | O pipeline YOLOv8l-pose + BoTSORT identifica e rastreia continuamente os dois participantes da sessão (guardião e criança) frame a frame, mesmo em casos de oclusão parcial ou saída temporária do quadro |
| **Classificação automática de papéis (Guardião / Criança)** | O sistema identifica qual dos dois indivíduos detectados é o guardião e qual é a criança por meio de análise de tamanho relativo (par-based prescan), eliminando a necessidade de configuração manual por sessão |
| **Estimativa de direção do olhar (gaze)** | O MediaPipe Face Mesh com detecção de íris permite estimar o vetor de gaze de cada participante, mesmo com rotação parcial da cabeça — métrica diretamente relacionada ao contato visual e ao indicador "Warm" |
| **Análise de postura corporal** | O YOLOv8l-pose extrai 17 keypoints do esqueleto de cada participante, possibilitando inferir o engajamento postural ao longo da sessão |
| **Cálculo de distância interpessoal** | A distância euclidiana entre os bounding boxes de guardião e criança é calculada frame a frame, gerando uma série temporal de proximidade física entre os participantes |
| **Geração de métricas comportamentais agregadas** | O sistema consolida as métricas frame a frame em indicadores por sessão: % de olhar mútuo, % de desvio de gaze, distância média, variância de postura e outros — insumos diretos para o classificador LSTM |
| **Classificação probabilística de risco TEA** | O classificador Bidirectional LSTM com attention pooling (GAIA LSTM v1) processa as métricas extraídas e retorna uma probabilidade P(TEA) com breakdowns por dimensão comportamental |
| **Exportação de relatório** | O sistema gera relatórios em PDF via ReportLab com as métricas da sessão, o indicador de risco e os insights automáticos, prontos para uso clínico |
| **Processamento em lote** | O pipeline suporta processar múltiplos vídeos em sequência com controle de fila e registro de sessões já processadas (processed.txt) |

---

#### 1.3 Restrições da Plataforma

| Restrição | Justificativa |
| :--- | :--- |
| **Requer GPU NVIDIA com CUDA** | O pipeline YOLOv8 e o MediaPipe operam com aceleração GPU para atingir performance viável (processamento próximo ao tempo real). Sem GPU compatível, o tempo de processamento torna-se inviável clinicamente |
| **Limitado a exatamente 2 pessoas por cena** | O sistema foi projetado e validado para díades (um guardião + uma criança). Cenas com mais de 2 pessoas ou com apenas 1 pessoa detectada são descartadas pelo mecanismo de controle de qualidade |
| **Câmera fixa e elevada recomendada** | Os pesos de estimativa de posição (camera_y_weight) foram calibrados para câmera com ângulo superior. Câmeras frontais ou móveis degradam a qualidade da classificação de papéis e do gaze |
| **Iluminação controlada** | O MediaPipe Face Mesh falha silenciosamente em condições de baixa luminosidade, caindo para o fallback YOLO que é menos preciso para estimativa de gaze |
| **Sem processamento em tempo real** | O sistema processa vídeos pré-gravados. Não há suporte a streams de câmera ao vivo na versão atual |
| **Armazenamento local obrigatório** | Os vídeos de sessão não são enviados para nenhum servidor externo — permanecem no dispositivo do clínico. Isso é uma restrição arquitetural deliberada para conformidade com a LGPD e com os termos éticos da UNSW |
| **Sem suporte a macOS / Linux na interface clínica** | A interface web local foi desenvolvida e testada em Windows. Suporte a outros sistemas operacionais requer validação adicional |
| **Dependência de qualidade mínima do vídeo** | Vídeos com menos de 50% de frames válidos (para sessões NT) ou 40% (para sessões TEA) são descartados do treinamento LSTM, pois não atingem limiar mínimo de confiabilidade |

---

### 2. Princípios Gerais do Projeto

> Conforme Barbosa e Silva (2010), esta etapa consiste na pesquisa e catalogação do conhecimento ergonômico disponível para a concepção da interface, considerando o contexto de uso (usuário, tarefa, equipamento e ambiente) no qual o sistema está inserido.

#### Contexto de Uso
O sistema GAIA é utilizado por **neuropsicólogos, psicólogos clínicos e demais especialistas em TEA** (Dra. Helena — persona primária), em ambiente clínico ou de pesquisa, em estações de trabalho desktop com Windows. O especialista interage com a interface para fazer upload de vídeos de sessões, acompanhar o processamento e interpretar os resultados de prognóstico gerados pela IA. O contexto envolve dados de saúde sensíveis de crianças, exigindo atenção redobrada a privacidade, segurança e clareza das informações apresentadas.

| Nome da Referência | Descrição e Relevância para o Projeto | Link |
| :--- | :--- | :--- |
| **LGPD — Lei nº 13.709/2018** | Lei Geral de Proteção de Dados Pessoais brasileira. Regula o tratamento de dados pessoais, incluindo dados sensíveis como imagens de crianças. O GAIA processa vídeos de menores de idade, tornando o cumprimento da LGPD obrigatório: os dados devem ser armazenados localmente, acessados apenas por profissionais autorizados e utilizados exclusivamente para a finalidade declarada (análise comportamental auxiliar ao diagnóstico). | [planalto.gov.br](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm) |
| **Lei de Acessibilidade — Lei nº 10.098/2000** | Estabelece normas gerais e critérios básicos para a promoção da acessibilidade de pessoas com deficiência. A interface do GAIA deve ser acessível a especialistas com deficiências visuais ou motoras, adotando contraste adequado, fontes legíveis e compatibilidade com leitores de tela. | [planalto.gov.br](https://www.planalto.gov.br/ccivil_03/leis/l10098.htm) |
| **ABNT NBR ISO 9241 — Ergonomia da Interação Humano-Sistema** | Norma internacional que define princípios de usabilidade para sistemas interativos, incluindo eficácia, eficiência e satisfação do usuário. Orienta as decisões de design da interface do GAIA, especialmente nos critérios de navegabilidade, clareza das métricas apresentadas e prevenção de erros no upload e classificação de vídeos. | [abnt.org.br](https://www.abnt.org.br) |
| **WCAG 2.1 — Web Content Accessibility Guidelines** | Diretrizes internacionais de acessibilidade para conteúdo web, definidas pelo W3C. Como a interface do GAIA é servida via navegador (localhost), as diretrizes de contraste mínimo (4.5:1), navegação por teclado e descrição de elementos interativos se aplicam diretamente. | [w3.org/WAI/WCAG21](https://www.w3.org/WAI/WCAG21/quickref/) |
| **Resolução CFM nº 2.299/2021** | Regulamenta o uso de Inteligência Artificial na Medicina no Brasil, estabelecendo que sistemas de IA devem atuar como ferramenta de apoio à decisão clínica — nunca substituindo o julgamento do médico ou especialista. O GAIA é explicitamente projetado como ferramenta auxiliar (copiloto), em conformidade com este princípio. | [cfm.org.br](https://www.cfm.org.br) |
| **Heurísticas de Nielsen (1994)** | Conjunto de 10 princípios de usabilidade amplamente adotados como guia de design de interfaces. Aplicados ao GAIA especialmente nos critérios de: visibilidade do status do sistema (barra de progresso do processamento), controle e liberdade do usuário (cancelar upload), prevenção de erros (alerta antes de classificar vídeo como TEA/Neurotípico) e ajuda e documentação. | [nngroup.com](https://www.nngroup.com/articles/ten-usability-heuristics/) |
| **Material Design 3 — Google** | Guia de estilo e sistema de design do Google para aplicações web e mobile. Utilizado como referência para padronização de componentes visuais da interface do GAIA: botões, cards, barras de progresso, toggles e tipografia — garantindo consistência visual e comportamento previsível para o usuário. | [m3.material.io](https://m3.material.io) |

---

### 3. Metas de Usabilidade

> Conforme Barbosa e Silva (2010), as metas de usabilidade definem as **exigências quantitativas e qualitativas** esperadas para o sistema, nos termos dos fatores básicos de usabilidade: eficácia, eficiência e satisfação do usuário.

#### 3.1 Exigências Qualitativas

| Meta | Descrição |
| :--- | :--- |
| **Facilidade de aprendizado** | Um especialista sem treinamento prévio deve conseguir realizar seu primeiro upload e interpretar o resultado sem necessidade de manual, apenas com os elementos da interface |
| **Clareza das métricas** | Os indicadores comportamentais (% olhar mútuo, distância interpessoal, P(TEA)) devem ser apresentados de forma que o especialista compreenda seu significado clínico sem formação em computação |
| **Prevenção de erros críticos** | O sistema deve alertar o usuário antes de ações irreversíveis ou de alto impacto, como a classificação de rótulo TEA/Neurotípico de um vídeo no dataset de treinamento |
| **Transparência da IA** | O sistema deve deixar claro que o resultado é uma estimativa de apoio à decisão — nunca um diagnóstico definitivo |
| **Privacidade por design** | Nenhum dado de paciente deve sair do dispositivo local sem consentimento explícito do usuário |

#### 3.2 Exigências Quantitativas

| Meta de Usabilidade | Indicador | Valor Mínimo Admissível | Justificativa |
| :--- | :--- | :--- | :--- |
| **Eficácia — Taxa de conclusão de tarefas** | % de usuários que completam o fluxo de upload + visualização de resultado sem ajuda externa | ≥ 85% | Especialistas clínicos têm perfil tecnológico intermediário (conforme levantamento da Entrega 7); a interface deve ser autoexplicativa para a maioria |
| **Eficiência — Tempo para primeira análise** | Tempo médio desde o login até a visualização do primeiro resultado de prognóstico | ≤ 5 minutos (excluindo tempo de processamento da IA) | A interação com a interface não deve ser o gargalo — o tempo de processamento do pipeline é inevitável, mas a navegação deve ser fluida |
| **Eficiência — Tempo de aprendizado** | Tempo para um usuário novo realizar a primeira tarefa principal sem erros | ≤ 10 minutos | Condizente com o perfil de usuário intermediário e com a complexidade reduzida do fluxo (Lei de Hick-Hyman aplicada ao design) |
| **Satisfação do usuário** | Pontuação mínima no questionário de satisfação pós-uso (escala Likert 1–5) | ≥ 4,0 / 5,0 | Ferramenta clínica precisa gerar confiança e conforto — satisfação baixa reduz adoção e pode levar ao abandono |
| **Prevenção de erros — Taxa de erro em classificação** | % de sessões classificadas com rótulo errado (TEA/Neurotípico) por falha de interface | ≤ 2% | Erro de classificação contamina o dataset de treinamento e compromete a validade do modelo LSTM — consequência clínica grave |
| **Facilidade de aprendizado — Retenção** | % de tarefas realizadas corretamente em segundo uso, sem treinamento adicional | ≥ 90% | Interface consistente deve permitir que o usuário retome o sistema após dias sem uso sem dificuldade |

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. Interação Humano-Computador. Elsevier, 2010. Editado por Plinio Aquino.*
---

## 🎭 Entrega 9: Cenários de Interação e Design
*Status: [Em andamento]*

### 1) Cenários de Interação
> [Reescrita do cenário problema, agora incluindo a interação com a solução GAIA]

### 2) Design Centrado na Comunicação (Diálogos)
| Tópico > Subtópico | Falas e Signos (U=Usuário, S=Sistema) |
| :--- | :--- |
| U: Preciso... | U: [Ação] |
| > | S: [Resposta/Tela] |

### 3) Mapa de Objetivos
> [Inserir diagrama]

### 4) Esquema Conceitual de Signos
| Signo | Origem | Tipo Conteúdo | Restrição | Prevenção | Recuperação |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Usuário** | Domínio | Texto | Não nulo | Campo Obrigatório | Mensagem de erro |
| **Vídeo** | Domínio | Arquivo | .mp4, .avi | Formato inválido | Re-upload |

---

## 🗺️ Entrega 10: Diagrama MOLIC
*Status: [Em andamento]*

### Diagrama de Interação
> [Inserir imagem do diagrama MOLIC desenhado]

---

## 🎨 Entrega 11: Protótipo de Alta Fidelidade
*Status: [Em andamento]*

### Link para o Figma
> [Inserir Link Aqui]

*(Inserir alguns prints das telas principais aqui no README)*

---

## 📊 Entrega 12: Planejamento de Usabilidade (DECIDE)
*Status: [Em andamento]*

### a) Planejamento (DECIDE)
* **D (Determinar):** Objetivos da avaliação.
* **E (Explorar):** Perguntas a serem respondidas.
* **C (Escolher):** Métodos de avaliação.
* **I (Identificar):** Questões práticas (participantes, equipamentos).
* **D (Decidir):** Como lidar com questões éticas.
* **E (Avaliar):** Como analisar os dados.

### b) Lista de Instrumentos
* [ ] Termo de Consentimento Livre e Esclarecido (TCLE)
* [ ] Roteiro de Tarefas
* [ ] Questionário Pós-Teste

---

## 🧐 Entrega 13: Avaliação Heurística
*Status: [Em andamento]*

### A) Violações Encontradas (Heurísticas de Nielsen)

| ID | Heurística Violada | Descrição do Problema | Grau de Severidade (0-4) | Local (Tela) |
| :--- | :--- | :--- | :--- | :--- |
| 1 | [Ex: Visibilidade do Status] | [O sistema não avisa quando o upload termina] | 3 (Grave) | Tela de Upload |

*Legenda Severidade:*
* 0: Sem importância
* 1: Cosmético
* 2: Simples
* 3: Grave
* 4: Catastrófico

### B) Boas Práticas (Exemplos de Sucesso)
> [Print de uma tela onde uma heurística foi muito bem aplicada]

---

## 🧪 Entrega 14: Avaliação por Observação
*Status: [Em andamento]*

### A) Fluxograma de Avaliação
> [Imagem do fluxo]

### B) Procedimento de Preparação
1.  Recrutamento.
2.  Setup do ambiente.
3.  Lista de Tarefas.

### C) Resultados do Teste (Exemplo de Tabela)
| Tarefa | Grau de Sucesso | Erros Cometidos | Tempo | Grau de Satisfação |
| :--- | :--- | :--- | :--- | :--- |
| **1. Fazer Upload** | Sucesso Total | 0 | 10s | Alto |
| **2. Gerar Relatório** | Sucesso Parcial | 1 (Confusão no botão) | 45s | Médio |

### Conclusão da Avaliação
> [Síntese dos resultados]

---
*Documentação gerada para a disciplina de Interface Humano-Computador (IHC) - 2026.*

















