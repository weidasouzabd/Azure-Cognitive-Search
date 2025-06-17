# Laboratório: Mineração de Conhecimento com Azure AI Search

Este repositório documenta um laboratório prático focado na aplicação de técnicas de organização e pesquisa de documentos utilizando ferramentas de Inteligência Artificial no Microsoft Azure. O objetivo é explorar como ingestão de dados, indexação e habilidades de IA podem ser usadas para minerar e extrair conhecimento de grandes volumes de informação.

## Sumário

1.  [Objetivo do Laboratório](#objetivo-do-laboratório)
2.  [Tecnologias Utilizadas](#tecnologias-utilizadas)
3.  [Pré-requisitos](#pré-requisitos)
4.  [Etapas do Laboratório](#etapas-do-laboratório)
    *   Criação dos Recursos Essenciais no Azure
    *   Ingestão e Carregamento dos Documentos
    *   Indexação e Enriquecimento de Dados com Habilidades de IA
    *   Consulta Prática do Índice de Pesquisa
    *   Revisão do Knowledge Store
5.  [Insights e Aprendizados](#insights-e-aprendizados)
6.  [Estrutura do Repositório](#estrutura-do-repositório)

## Objetivo do Laboratório

O laboratório teve como meta principal demonstrar, de forma prática, o processo de construção de uma solução de mineração de conhecimento. Especificamente, focou em:

*   Ingerir dados (documentos não estruturados) em uma plataforma de IA.
*   Criar índices pesquisáveis e inteligentes usando o Azure AI Search.
*   Enriquecer o conteúdo dos documentos com insights gerados por serviços de IA (Azure AI Services).
*   Explorar e consultar os dados organizados e enriquecidos para extrair informações relevantes.

Utilizamos como estudo de caso avaliações de clientes de uma cafeteria fictícia (Fourth Coffee) para ilustrar a aplicação dessas técnicas.

## Tecnologias Utilizadas

*   **Azure AI Search:** Serviço principal para indexação, busca e pipeline de processamento de dados.
*   **Azure AI Services:** Fornece habilidades cognitivas (detecção de sentimento, extração de frases-chave/localizações, OCR, etc.) para enriquecer os dados.
*   **Azure Storage Account:** Utilizado para armazenar os documentos brutos e o *Knowledge Store* com os dados enriquecidos.

## Pré-requisitos

Para replicar este laboratório, você precisará de:

*   Uma assinatura ativa do Microsoft Azure.
*   Acesso ao portal do Azure para criação e configuração dos recursos.
*   Conhecimento básico sobre serviços de nuvem do Azure.
*   Os arquivos de dados de exemplo (neste caso, as avaliações de café baixadas de `https://aka.ms/mslearn-coffee-reviews`).

## Etapas do Laboratório

As seguintes etapas foram realizadas para configurar e executar o pipeline de mineração de conhecimento:

### Criação dos Recursos Essenciais no Azure

Provisionamento e configuração dos recursos **Azure AI Search**, **Azure AI Services** (no mesmo local) e **Azure Storage Account** (com acesso anônimo de Blob habilitado) no portal do Azure.

### Ingestão e Carregamento dos Documentos

Criação de um contêiner de blob (`coffee-reviews`) na conta de armazenamento e upload dos arquivos de avaliação de café para este contêiner.

### Indexação e Enriquecimento de Dados com Habilidades de IA

Configuração e execução do pipeline de indexação utilizando o assistente de Importação de Dados do Azure AI Search:

*   Definição da **Fonte de Dados** conectada ao contêiner de blobs.
*   Criação de um **Skillset** (`coffee-skillset`) aplicando habilidades cognitivas (detecção de sentimento, extração de frases-chave, etc.) para enriquecer o conteúdo.
*   Configuração do **Knowledge Store** para persistir os dados enriquecidos em projeções (JSON, imagens) e tabelas na conta de armazenamento.
*   Criação do **Índice** (`coffee-index`) com os campos relevantes marcados como pesquisáveis e filtráveis.
*   Criação e execução do **Indexador** (`coffee-indexer`) para automatizar o processo.

### Consulta Prática do Índice de Pesquisa

Utilização do Search Explorer no portal do Azure AI Search para testar a capacidade de busca e filtragem do índice (`coffee-index`) com diferentes critérios (ex: busca geral, filtro por localização, filtro por sentimento negativo).

### Revisão do Knowledge Store

Exploração da conta de armazenamento para visualizar os dados enriquecidos persistidos no *Knowledge Store*, incluindo as projeções JSON e as tabelas com informações extraídas (como `coffeeSkillsetKeyPhrases`), demonstrando como os dados podem ser estruturados para análise posterior.

## Insights e Aprendizados

*   O Azure AI Search oferece uma solução integrada para criar motores de busca potentes e inteligentes.
*   A combinação do AI Search com o AI Services permite transformar dados não estruturados em informações ricas e pesquisáveis.
*   O *Knowledge Store* é uma funcionalidade valiosa que torna os insights extraídos pela IA persistentes e acessíveis para outras aplicações ou análises.
*   O laboratório reforça a importância de definir corretamente a fonte de dados, o skillset, o índice e o indexador para um pipeline de mineração de conhecimento eficiente.
*   A consulta do índice e a exploração do *Knowledge Store* são passos cruciais para validar o processo e entender o valor dos dados enriquecidos.

## Estrutura do Repositório

Este repositório contém:

*   `README.md`: Este arquivo, descrevendo o laboratório.
*   (Outros arquivos ou pastas para registrar as etapas, como screenshots, notas, etc.)
