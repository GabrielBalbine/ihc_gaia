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

#### 2. Status
* **Papel:** Neuropsicóloga Infantil e Pesquisadora.
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

1.  **Sessão:** Helena grava a interação com a criança, tentando anotar pontos chave na prancheta (atenção dividida).
2.  **Extração:** Transfere o arquivo da câmera para o PC.
3.  **Análise Manual (Gargalo):** Abre o vídeo, assiste, pausa, anota o tempo, volta o vídeo. Repete isso por horas.
4.  **Impacto Pessoal:** Chega em casa tarde, cansada, e ainda precisa somar os tempos para o laudo. Perde o jantar com a família.
5.  **Laudo:** Entrega um relatório subjetivo, sentindo que poderia ser mais precisa.
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




