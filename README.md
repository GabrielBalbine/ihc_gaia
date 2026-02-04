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
> *[ANÁLISE DE PADRÕES
COMPORTAMENTAIS NO TEA: DESAFIOS
DIAGNÓSTICOS E NOVAS FERRAMENTAS
TECNOLÓGICAS]*

### 1.3) Nome do Orientador
* Prof. [NOME DO ORIENTADOR]

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

## 🔍 Entrega 2: Análise de Concorrência
*Status: [Em andamento]*

### 1) Público Alvo
> [Descrever brevemente o perfil do público alvo mapeado]

### 2) Análise de Concorrência (Soluções Similares)
*ATENÇÃO: Concorrente não é idêntico, e sim atuando na mesma área.*

#### A. Principais concorrentes (Softwares de Análise Comportamental/Triagem)
| Nome | Link | Descrição |
| :--- | :--- | :--- |
| **[Nome Concorrente 1]** | [URL] | [Breve descrição] |
| **[Nome Concorrente 2]** | [URL] | [Breve descrição] |

*(Inserir prints das telas dos concorrentes na pasta `/docs/img` e linkar aqui)*

#### B. Características e funcionalidades dos concorrentes
* [Funcionalidade 1]
* [Funcionalidade 2]

#### C. Experiência do usuário (UX) e Opiniões
> [Resumo de reviews ou percepção de uso]

#### D. Preços e modelos de negócio
* [Ex: Assinatura mensal, Licença única, Gratuito]

#### E. Padrões e tendências no mercado
* [Ex: Uso de IA, Dashboards simplificados, Mobile first]

---

## 👤 Entrega 3: Personas e Contexto
*Status: [Em andamento]*

### 1) Personas
> [Inserir descrição ou imagem da Persona criada]

### 2) Mapa de Empatia
> [Inserir imagem do Mapa de Empatia]

### 3) Contexto de Uso
> [Descrição detalhada do cenário onde o sistema é usado]

### 4) Jornada do Usuário
> [Inserir imagem ou descrição passo-a-passo da jornada atual]

---

## ⚠️ Entrega 4: Cenários de Análise (Problema)
*Status: [Em andamento]*

*Dica: Cenário de Análise é uma "história triste". Descreve apenas o problema atual, sem a solução.*

### 1) Cenário de Análise/Problema
> [Escrever a narrativa do problema enfrentado pelo usuário hoje]

### 2) Questões de Refinamento
* [Questão 1]
* [Questão 2]

### 3) Refinamento do Cenário
> [Versão melhorada do cenário acima]

---

## 🛠️ Entrega 5: Análise de Tarefas
*Status: [Em andamento]*

*Cada aluno deve modelar pelo menos 1 diagrama de cada tipo.*

### 1) HTA (Hierarchical Task Analysis)
> [Inserir Diagrama HTA]
> *Explicação:*

### 2) GOMS (Goals, Operators, Methods, Selection rules)
> [Inserir Modelo GOMS]
> *Explicação:*

### 3) CTT (ConcurTaskTrees)
> [Inserir Árvore de Tarefas CTT]
> *Explicação:*

---

## 📝 Entrega 6: Prototipação de Baixa Fidelidade
*Status: [Em andamento]*

### Protótipo em Papel
> [Inserir fotos dos desenhos/rascunhos das telas]

---

## 📋 Entrega 7: Requisitos e Ética
*Status: [Em andamento]*

### 1) Identificação de Necessidades e Requisitos
* **Que dados coletar?** [Resposta]
* **De quem coletar?** [Resposta]

### 2) Aspectos Éticos
> [Justificativa sobre ética, consentimento e privacidade de dados sensíveis]

### 3) Ferramentas de Coleta de Dados
* **Instrumento:** [Ex: Questionário, Entrevista]
* **Como aplicar:** [Procedimento]
* **Link/Roteiro:** https://www.collinsdictionary.com/dictionary/portuguese-english/ou

---

## 🔄 Entrega 8: Engenharia de Usabilidade
*Status: [Em andamento]*

### 1. Características da Plataforma
| Característica | Descrição |
| :--- | :--- |
| **Descrição do Software** | [Web/Desktop, Linguagem, etc] |
| **Descrição do Hardware** | [Requisitos mínimos, Câmera, Processamento] |
| **Capacidades** | [O que o sistema consegue fazer] |
| **Restrições** | [Limitações técnicas ou de ambiente] |

### 2. Princípios Gerais do Projeto (Legislação e Normas)

| Nome | Descrição | Link | Descrição do Contexto no Projeto |
| :--- | :--- | :--- | :--- |
| **LGPD (Lei 13.709/2018)** | Lei que regulamenta o tratamento de dados pessoais no Brasil. | [Planalto](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm) | Estabelece regras sobre coleta e proteção dos vídeos e dados dos pacientes (crianças). |
| **Lei da Acessibilidade (10.098/2000)** | Normas gerais e critérios básicos para a promoção da acessibilidade. | [Planalto](https://www.planalto.gov.br/ccivil_03/leis/l10098.htm) | Diretrizes para tornar a interface acessível a profissionais com deficiência. |
| **ABNT NBR ISO 9241** | Ergonomia da interação humano-sistema. | - | Princípios de design centrado no usuário para garantir usabilidade. |

### 3. Metas de Usabilidade
| Metas (Qualitativo/Quantitativo) | Porcentagem | Justificativa |
| :--- | :--- | :--- |
| **Facilidade de Aprendizado** | [X]% | [Motivo] |
| **Eficiência de Uso** | [X]% | [Motivo] |
| **Prevenção de Erros** | [X]% | [Motivo] |
| **TOTAL** | **100%** | |

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
