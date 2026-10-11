# Acervo Inep: Enade Medicina e Enamed

Inclusão solicitada por Jean em 11/10/2026.

## Estado real

Fontes cadastradas em [data/sources/inep.json](../data/sources/inep.json).
Nenhum PDF foi baixado e nenhuma questão foi extraída ou publicada. O repositório ainda está na fase de planejamento, sem aplicação ou banco de dados operacional.

## Fontes iniciais

| Fonte | Material | Endereço |
|---|---|---|
| Enade | Índice oficial por edição; selecionar Medicina | https://www.gov.br/inep/pt-br/areas-de-atuacao/avaliacao-e-exames-educacionais/enade/provas-e-gabaritos |
| Enade Medicina 2023 | Caderno, gabarito e padrão de respostas discursivas | https://riep.inep.gov.br/items/41394cd9-fcb6-4d49-b5b2-343fde7d8bbf |
| Enamed | Índice oficial com edições 2025 e 2026 na consulta de 11/10/2026 | https://www.gov.br/inep/pt-br/areas-de-atuacao/avaliacao-e-exames-educacionais/enamed/provas-e-gabaritos |

A presença da edição não significa que seu gabarito seja definitivo. Conferir a identificação de cada documento antes da importação. Edições antigas de Medicina serão catalogadas após verificação individual; não presumir que todo ano do índice Enade contém Medicina.

## Requisitos da importação

1. Consultar o catálogo e resolver os links dos documentos no portal oficial.
2. Registrar URL do arquivo, data da consulta, edição, tipo de caderno e versão do gabarito.
3. Baixar para armazenamento de conteúdo separado do repositório público e calcular hash do arquivo.
4. Extrair enunciados, alternativas, figuras e tabelas preservando a associação com cada questão. Encaminhar OCR ou extrações ambíguas para revisão.
5. Vincular respostas somente ao caderno correspondente. Manter gabaritos preliminares, definitivos e retificações como versões diferentes.
6. Registrar anulações sem contabilizá-las como erros dos alunos; evitar duplicação entre versões ampliadas do mesmo caderno.
7. Classificar especialidade e tema como metadados editoriais revisáveis. Separar formação geral de conteúdo médico específico.
8. Conferir todos os enunciados e gabaritos importados com os documentos originais antes de disponibilizar.
9. Gerar comentários pedagógicos em campo separado, identificados como conteúdo editorial ou de IA. Não chamar comentários próprios de explicações oficiais do Inep.
10. Verificar condições de reutilização e imagens de terceiros antes de disponibilização comercial. A disponibilidade pública do PDF não é tratada pelo sistema como licença irrestrita.

## Dados mínimos da questão

Identificador; exame; edição; caderno; número original; tipo objetiva/discursiva; enunciado; alternativas; figuras e respectivas páginas; gabarito e versão; estado válida/anulada/retificada; padrão discursivo quando existente; fonte e URL; hash do documento; área; tema; estado da revisão; comentário pedagógico e suas referências.

## Interface prevista

Filtros por Enade/Enamed, ano, área e tema; link para fonte; indicação de gabarito preliminar ou definitivo; marcação de anuladas; resposta antes da revelação do gabarito; explicação separada do documento oficial; botão para reportar erro de transcrição.

## Critérios de aceitação

- Quantidade de questões e numeração correspondem ao caderno original.
- Cada questão pode ser rastreada até o documento e página.
- Nenhum gabarito de outro caderno é associado por aproximação.
- Figuras e tabelas ausentes bloqueiam a publicação da questão.
- Questões anuladas não prejudicam desempenho.
- Retificações preservam histórico e permitem recalcular resultados.
- Não publicar questões sem revisão de extração e gabarito.

## Próxima tarefa para o Codex

Quando a implementação for autorizada, usar este catálogo para construir uma importação revisável. Começar pela edição Enade Medicina 2023, medir qualidade da extração e só então expandir. Não simular que as questões já foram importadas.
