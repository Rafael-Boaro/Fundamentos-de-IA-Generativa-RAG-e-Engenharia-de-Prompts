# Caderno Temático: Fundamentos de IA Generativa e RAG com NotebookLM

Repositório desenvolvido para o desafio **"Acelere sua Aprendizagem com IA: Explore o Poder do NotebookLM"** da plataforma [DIO](https://www.dio.me/). 

Este projeto explora o uso de Inteligência Artificial como ferramenta de aprendizado ativo, curadoria de conhecimento e documentação técnica, aplicando o NotebookLM para sintetizar conceitos complexos de IA Generativa e Sistemas de Recuperação de Informação.

---

## 1. Contexto e Objetivos

### Assunto de Interesse
O tema escolhido para este caderno temático é **Sistemas baseados em RAG (Retrieval-Augmented Generation) e Otimização de Engenharia de Prompts**. 

### Objetivos de Estudo
- Compreender a arquitetura de funcionamento do RAG, que serve como base para o próprio NotebookLM.
- Identificar as melhores práticas na elaboração de prompts para extração, sumarização e ideação a partir de fontes documentais longas.
- Mapear limitações (alucinações) e técnicas de mitigação no uso de LLMs para análise de documentos técnicos.

---

## 2. Tecnologias e Conceitos Aplicados

| Camada | Tecnologia / Conceito | Finalidade |
|---|---|---|
| Ingestão e Curadoria | Google NotebookLM | Ambiente de consolidação e grounding documental |
| Modelo Base de Linguagem | Gemini 1.5 Pro | Raciocínio sobre contexto longo e síntese técnica |
| Recuperação de Informação | RAG (Retrieval-Augmented Generation) | Ancoragem de respostas com base em vetores semânticos |
| Engenharia de Prompts | Roleplay, Delimitadores e Few-Shot | Redução de alucinações e padronização de saídas |

---

## 3. Curadoria de Fontes

Para alimentar a base de conhecimento do NotebookLM, foram selecionadas **4 fontes públicas e confiáveis**, cobrindo desde a teoria acadêmica até a aplicação prática:

1. **[Artigo Original do RAG - Meta AI / arXiv]**: *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks* (Lewis et al., 2020). Base teórica fundamental sobre como unir geração de texto com recuperação externa.
2. **[Documentação Oficial do Google Cloud]**: *Guia de Engenharia de Prompts para o Gemini*. Regras e estruturas recomendadas para extrair o máximo raciocínio do modelo.
3. **[Blog Oficial do Google]**: *Apresentando o NotebookLM e o poder do Gemini 1.5 Pro com janela de contexto longa*.
4. **[Guia de Boas Práticas em IA Generativa]**: Artigos técnicos sobre redução de alucinações e ancoragem de respostas (grounding).

*(Nota: Todos os arquivos em PDF e textos brutos foram carregados diretamente como fontes no painel do NotebookLM).*

---

## 4. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Durante a exploração do NotebookLM, vários ciclos de iteração foram testados para refinar as respostas. Abaixo estão documentados os testes, ajustes e aprendizados:

### Teste 1: Busca Direta (Prompting Ingênuo)
- **Prompt Utilizado**: *"O que é RAG e como ele funciona?"*
- **Resultado Obtido**: Uma resposta correta, porém superficial e genérica, sem referenciar diretamente os detalhes técnicos dos PDFs carregados.
- **Dificuldade / "Cicatriz"**: O modelo tendeu a usar seu conhecimento prévio geral em vez de focar estritamente nas especificidades arquiteturais detalhadas nos papers da fonte.

### Teste 2: Prompting Estruturado com Delimitadores e Papel (Roleplay)
- **Prompt Utilizado**: 
  ```text
  Atue como um Arquiteto de Software especialista em IA. 
  Com base exclusivamente nas fontes fornecidas, elabore uma explicação técnica sobre o fluxo de dados em um sistema RAG. 
  Divida a resposta em três etapas: 1. Ingestão/Chunking, 2. Recuperação (Retrieval) e 3. Geração. 
  Cite o número da fonte ao final de cada afirmação técnica.
  ```
- **Resultado Obtido**: Resposta altamente estruturada, com distinção precisa entre o papel do Retriever (busca densa de vetores via similaridade semântica) e do Generator (LLM sintetizando o prompt acrescido de contexto), com referência explícita aos artigos de base.
- **Aprendizado**: Atribuir persona técnica e exigir divisão estruturada por fases força o modelo a seguir a lógica conceitual dos documentos ancorados.

---

## 5. Decisões Técnicas e Conclusões

- **Ancoragem estrita (Grounding):** A delimitação do escopo para responder estritamente com base nos documentos carregados elimina alucinações conceituais comuns em modelos de linguagem puros.
- **Citação rastreável:** Exigir numeração ou menção de fonte assegura auditabilidade da informação, um requisito primordial em ambientes corporativos de análise de dados e tomada de decisão.
- **Aceleração do aprendizado técnico:** O uso de RAG pessoal reduz o tempo de síntese de papers acadêmicos e documentações densas sem perda de profundidade técnica.
