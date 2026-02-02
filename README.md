# 🌍 Projeto GAIA (IHC Edition)

Este repositório contém a documentação e o código fonte do projeto **GAIA**, desenvolvido como Trabalho de Conclusão de Curso (TCC) e adaptado para a disciplina de Interface Humano-Computador (IHC).

## 📋 Definições do Projeto

O GAIA é uma ferramenta de **apoio ao prognóstico** de Transtorno do Espectro Autista (TEA) baseada em Visão Computacional. O sistema foca na análise objetiva de vídeos para auxiliar profissionais na tomada de decisão clínica.

### 1) Membros de Equipe
* **Gabriel Balbine de Andrades** - Matrícula: `22.222.001-4`

### 2) Título Original do TCC
> *Aplicação de Visão Computacional como Ferramenta de Apoio ao Prognóstico de TEA*

### 3) Nome do Orientador
* Prof. Victor Varela Perrone

### 4) Previsto desenvolver Interface?
- [x] Sim
- [ ] Não

### 5) Objetivo do trabalho
Desenvolver uma solução tecnológica para **auxílio ao prognóstico**, processando vídeos de interações sociais para identificar padrões comportamentais típicos do espectro autista, fornecendo dados quantitativos para embasar a decisão médica.

### 6) Produto Final
Um sistema desktop/web dividido em dois ambientes:
1.  **Ambiente de Treinamento (Admin):** Para curadoria e alimentação do dataset.
2.  **Ambiente Clínico (Usuário):** Para upload de vídeos de pacientes e visualização de dashboards de risco.

### 7) Público-Alvo (Usuário Final)
* Psiquiatras
* Psicólogos
* Pesquisadores da área de neurodesenvolvimento
* *(Não destinado ao uso por pais ou pacientes diretamente)*

### 8) Benefícios para o Usuário
* **Objetividade:** Transforma observações subjetivas em métricas quantificáveis.
* **Triagem Eficiente:** Indica rapidamente se um vídeo contém padrões que justificam uma investigação clínica aprofundada.
* **Apoio à Decisão:** Fornece relatórios visuais que servem como documentação complementar ao laudo médico.

### 9) Funcionalidades Principais
**Módulo Admin (Dataset):**
* [ ] Ingestão de vídeos brutos para o banco de dados.
* [ ] Rotulagem e refinamento do modelo.

**Módulo Especialista (Clínico):**
* [ ] Upload de vídeos de sessões (análise assíncrona/pós-processamento).
* [ ] Processamento via IA (YOLO + MediaPipe).
* [ ] **Dashboard de Insights:** Gráficos de contato visual, expressões e movimentação.
* [ ] **Indicador de Relevância:** Alerta automático sugerindo "Averiguação Aprofundada" baseado nos padrões detectados.

### 10) Tecnologias
* **Backend/Core:** Python, YOLO, MediaPipe.
* **Interface:** [Streamlit / React / etc].
* **Infraestrutura:** Docker.

### 11) Contexto de Uso
A ferramenta é utilizada em **ambiente controlado (consultório)**, de forma **assíncrona**. O profissional submete o vídeo após a consulta e utiliza o relatório gerado para estudar o caso antes de fechar um diagnóstico.

---
*Documentação gerada para a disciplina de IHC - 2026.*
