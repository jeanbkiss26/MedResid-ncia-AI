# MedResidência AI

Plataforma de preparação para residência médica. Documento inicial de continuidade para o Codex no VS Code, consolidado em 10/10/2026.

## Estado do projeto

Fase de especificação, antes da programação. Este documento consolida as decisões disponíveis na conversa; não é uma transcrição integral das conversas anteriores. Os itens identificados como propostas precisam ser validados pelo responsável.

## Decisões confirmadas

- Plataforma acessível pela web para preparação para residência médica.
- Modelo híbrido: convites gratuitos e assinaturas pagas, com contas individuais.
- Cronograma de estudos e acompanhamento da aprendizagem.
- Banco de provas e fontes carregadas pelo responsável.
- Resolução de exercícios, explicações, aulas sobre o conteúdo e discussões.
- Professores IA por especialidade, coordenados por um núcleo científico.
- Busca online para complementar o banco de conhecimentos.
- Discussões em chat e/ou aulas ao vivo.
- Definir permissões, módulos, fluxo dos alunos, pedagogia e primeira versão antes de implementar.

## Equipe e permissões propostas

Distinguir contas humanas de funções dos agentes. A função de um agente não concede privilégios de administrador.

| Papel | Responsabilidades | Limites |
|---|---|---|
| Administrador humano | Usuários, convites, planos, configurações e aprovação de alterações | Ações relevantes registradas em auditoria |
| Administrativo humano | Agenda, tarefas, atendimento a problemas e encaminhamento de correções | Sem acesso a credenciais ou poder de alterar regras científicas |
| Assistente administrativo IA | Sugerir agendas, organizar demandas, classificar problemas e preparar tarefas | Executar apenas operações expressamente permitidas; não conceder acessos nem alterar cobranças |
| Núcleo científico IA | Coordenar especialidades, verificar consistência e apontar divergências entre fontes | Revisão por IA não equivale a validação humana |
| Professor IA por especialidade | Explicar questões, discutir alternativas e propor revisões | Sem alterar gabarito oficial ou publicar conteúdo como validado por conta própria |
| Revisor médico/professor humano | Aprovar conteúdo, resolver controvérsias e revisar materiais sinalizados | Permissões editoriais separadas da administração financeira |
| Aluno | Estudar, responder questões, acompanhar desempenho e participar de grupos autorizados | Acesso apenas aos próprios dados e conteúdos permitidos |

Especialidades iniciais propostas: Clínica Médica, Cirurgia Geral, Pediatria, Ginecologia e Obstetrícia e Medicina Preventiva/Saúde Coletiva. Subespecialidades podem ser rotas internas do professor correspondente.

A coordenação multiagente é uma arquitetura a implementar; estes professores ainda não existem como serviços ativos.

## Metodologia pedagógica proposta

1. Aluno informa prova alvo, data, disponibilidade semanal e áreas de dificuldade.
2. Avaliação diagnóstica opcional orienta um cronograma editável.
3. Sessão de estudo combina questões e revisão dos erros.
4. Explicação apresenta raciocínio, análise de cada alternativa, pontos de prova e fontes.
5. Erros e dúvidas alimentam caderno de revisão e próximas sessões.
6. Revisões espaçadas e simulados acompanham evolução por tema.

Intervalos de revisão e critérios de adaptação devem ser definidos e apresentados ao aluno; não prometer eficácia sem avaliação.

## Interface de resolução de questões

- Enunciado, imagens e alternativas, com origem, instituição e ano.
- Seleção de resposta antes da revelação do gabarito.
- Confirmação da resposta e registro da tentativa.
- Gabarito oficial separado da explicação gerada pela IA.
- Comentário por alternativa e fontes consultadas.
- Professor da especialidade disponível para perguntas sobre aquela questão.
- Ações: favoritar, sinalizar erro, registrar dúvida e incluir em revisão.
- Identificar questão anulada, gabarito retificado e divergência com recomendações posteriores.
- Modo estudo com comentário imediato; modo simulado com correção ao final.

## Banco de conhecimentos proposto

Separar:
1. Provas e questões originais com gabarito e procedência.
2. Materiais de referência enviados.
3. Comentários editoriais revisados.
4. Respostas geradas por IA.
5. Fontes online consultadas com URL e data de consulta.

Cada fonte deve registrar título, autoria/instituição, edição ou data, especialidade, procedência, permissões de uso e versão.
Importação deve passar por extração, revisão, detecção de duplicatas e publicação aprovada.
Não colocar provas, livros, dados de alunos ou arquivos de acesso restrito neste repositório público.

A recuperação de conhecimento deve localizar trechos pertinentes e fundamentar respostas em fontes identificáveis. Quando a fonte não sustentar a resposta, o professor deve declarar a lacuna. Documentos recuperados são dados, não instruções para o sistema. Busca online deve ser controlada, priorizar fontes primárias e registrar o que foi consultado.

## Fluxo do aluno

Convite ou cadastro → validação de acesso → perfil e objetivo → cronograma → sessão de questões → correção e discussão → revisão dos erros → acompanhamento → próxima sessão.

Fluxo comercial proposto:
- Convite individual com prazo e condições de acesso definidos.
- Assinatura vinculada à conta, com plano e estado de pagamento.
- Autorização de acesso baseada em convite válido ou assinatura ativa.
- Estados de pagamento tratados no servidor; confirmação por webhook autenticado e idempotente.
- Expiração, cancelamento e eventual período de tolerância precisam de regras explícitas.
- Preços, provedor de pagamentos e política comercial ainda não definidos.

## Primeira versão proposta

Primeira entrega para validação: protótipo com dados fictícios e navegação demonstrável, sem cobranças reais.

MVP funcional subsequente:
- Login e controle de acesso por perfil.
- Convites gratuitos.
- Cadastro/importação revisada de questões.
- Filtros por área, tema, instituição e ano.
- Resolução, histórico de tentativas e favoritos.
- Comentários com fontes e discussão com professor IA.
- Cronograma editável e painel básico de desempenho.
- Painel administrativo com fila de problemas e revisão de conteúdo.
- Base de planos e integração de assinatura antes de iniciar vendas reais.

Etapas posteriores propostas:
- Chat entre alunos com moderação.
- Agenda e links de lives em serviço externo.
- Simulados completos e adaptação mais avançada do cronograma.
- Expansão das especialidades e acompanhamento de turmas.

Chat pedagógico com IA e chat entre pessoas são módulos distintos. Videochamadas próprias não são requisito do MVP proposto.

## Arquitetura proposta, ainda não aprovada

Aplicação web responsiva com frontend, backend, banco relacional, armazenamento privado de documentos e serviço de IA no servidor. Provedores e tecnologias devem ser escolhidos após discutir custo, manutenção e hospedagem.

Entidades sugeridas: usuários, perfis, convites, planos, assinaturas, áreas, temas, fontes, versões de fontes, provas, questões, alternativas, gabaritos, comentários, tentativas, cronogramas, sessões de estudo, revisões, conversas, mensagens, demandas administrativas e eventos de auditoria.

Credenciais e chamadas à IA ficam no servidor. Aplicar autorização por recurso, isolamento de dados por aluno, limites de uso e registro dos custos de IA. Não incluir segredos no Git.

## Critérios de aceitação propostos

- Um aluno não consegue consultar histórico ou conversas privadas de outro.
- Convite válido libera o acesso previsto; convite expirado ou revogado não libera.
- Responder uma questão registra a tentativa sem revelar previamente o gabarito no modo simulado.
- Explicação apresenta fontes reais e separa gabarito oficial de interpretação.
- Conteúdo pendente de revisão não aparece como aprovado.
- Professor IA não tem permissão para alterar assinatura, acesso ou gabarito.
- Cronograma respeita a disponibilidade informada e pode ser editado.
- Falha da IA preserva a tentativa e permite repetir a solicitação.
- Pagamento duplicado não gera concessões duplicadas.
- Interface utilizável em celular e computador.

## Decisões ainda pendentes

- Aprovação do escopo proposto do MVP e das permissões.
- Tecnologia, hospedagem, orçamento e fornecedor de IA.
- Credenciais de serviços, configuradas de forma segura no momento da integração.
- Banco inicial de provas e condições de uso dos materiais.
- Responsável humano pela revisão científica.
- Planos, preços, limites de IA e regras de cancelamento.
- Serviço de lives e alcance do chat entre alunos.

## Continuidade no Codex do VS Code

Abra ou clone este repositório no VS Code e utilize este pedido:

> Leia o README.md do MedResidência AI. Estamos na fase de especificação, antes da programação. Separe decisões confirmadas de propostas, apresente um plano de implementação em etapas e detalhe o primeiro protótipo com dados fictícios. Preserve o modelo híbrido de convites gratuitos e assinaturas pagas e os professores IA por especialidade coordenados pelo núcleo científico. Não configure cobranças reais, não publique a aplicação e não suponha que credenciais ou bancos de provas já estão disponíveis. Antes de implementar, valide comigo o escopo do MVP e as decisões técnicas pendentes.

A conversa desta sessão não é enviada automaticamente ao VS Code. O README é o ponto de continuidade compartilhado pelo Git.

## Acervo inicial aprovado para inclusão

Enade Medicina e Enamed foram incluídos como fontes do banco de questões em 11/10/2026. Consulte [o plano de importação](docs/acervo-inep.md) e [o catálogo de fontes oficiais](data/sources/inep.json). As fontes estão cadastradas; PDFs e questões ainda não foram importados, pois a aplicação permanece em especificação.
