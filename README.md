# Sprint_gestao-agil-proj-e-prod

# ✈️ SMARTTRAVEL // Corporate Travel Request & Compliance Platform

Workflow de solução:
- Começou mapeando o escopo através do Workshop Lean Inception no Miro (Passos 1 a 9).
- Estruturou o Product Backlog emergente por Épicos e Histórias de Usuário refinadas de acordo com as telas reais do sistema.
- Estabeleceu critérios rigorosos de prontidão (DoR) e conclusão (DoD) individuais e globais para governança do código.
- Consolida o encerramento do MVP com o planejamento tático e capacidade técnica medidos na Sprint 1 (Sprint Backlog).

## 0. Destaques de Governança e Engenharia de Requisitos

A governança do ecossistema SmartTravel conectou as diretrizes de qualidade orçamentária e compliance da OffshoreOne com o fluxo de trabalho real da equipe de engenharia durante a execução do projeto, operando através de pilares fundamentais:

#### 1. DoR (Definition of Ready) da Solução e Sua Origem no Planejamento Ágil
O Definition of Ready (DoR) que deu o sinal verde para o início do desenvolvimento técnico nasceu formalmente no fechamento do workshop Lean Inception e no rito de refinamento do backlog. O critério de prontidão humano estabelecido exige que nenhuma história entre em planejamento sem estrutura padrão (Como/Quero/Para), critérios de aceitação mapeados em BDD (Dado/Quando/Então) e o respectivo apoio do wireframe do Figma anexado. Uma vez cumpridos esses critérios analógicos de prontidão, o time iniciou a Sprint 1, garantindo que o desenvolvedor tenha insumos claros de engenharia de software antes de codificar.

#### 2. Manifesto de Engenharia e Variabilidade do DoD Técnico
Os critérios do Definition of Done (DoD) da solução não são engessados de forma genérica, variando de acordo com as especificidades técnicas e riscos arquiteturais de cada tela. Na execução prática, essa variabilidade se consolida nas descrições individuais dos cards: histórias críticas de formulário (como o módulo de captação de dados ST-02) trazem critérios rígidos de persistência em banco e validação de regras de negócio, enquanto módulos puramente de visualização (como o stepper visual ST-05) focam em critérios de consumo de APIs e responsividade de layout. O DoD técnico, portanto, tangibiliza o nível de rigor exigido pelo padrão de arquitetura do sistema.

#### 3. Acordo de Entrega e Requisitos Não Funcionais (RNF) Universais como DoD de Processo
No nível de segurança e governança corporativa, o time estabeleceu na concepção do projeto duas regras não funcionais inegociáveis como DoD de processo universal:
- **Auditoria Obrigatória:** Toda alteração de status da requisição (Aguard. Gerente, Aguard. Cost Control, Aprovado, Reprovado) deve disparar a gravação automática de um log de auditoria imutável no banco de dados, registrando a data, a hora exata e o ID do usuário responsável pela ação.
- **Segurança de Infraestrutura:** Todo o tráfego da aplicação, dados de perfis e trâmite de anexos deve ser criptografado, operando 100% sob protocolo seguro HTTPS. Nenhuma entrega é movida para "Done" sem a validação desses critérios pelo QA Felipe.

---

## 🎯 1. Cenário de Negócio e Contexto do Produto (OffshoreOne)
O **SmartTravel** é um sistema de gestão de viagens corporativas e compliance automatizado, projetado para eliminar falhas operacionais, descentralização e lentidão no fluxo de viagens da OffshoreOne.
* **A Dor Central:** O processo anterior de solicitação de viagens (Travel Request) dependia de planilhas locais e e-mails que se perdiam nas caixas de entrada. Isso gerava atrasos crônicos na compra de passagens (inflacionando tarifas de última hora), falta de visibilidade para auditoria externa e sobrecarga nos gestores.
* **A Solução:** Um workflow digitalizado e centralizado que amarra a criação da requisição a regras rígidas de compliance orçamentário por centro de custo, passando por uma esteira clara de aprovações antes da emissão de bilhetes.
* **Time Scrum Enxuto:** 
  * Thiago (Product Owner)
  * Mariana (Scrum Master)
  * Rodrigo (Desenvolvedor Full-Stack)
  * Vanessa (UX/UI Designer)
  * Felipe (QA Tester)

---

## 📈 2. Linha de Evolução e Esteira de Workflow

O SmartTravel estabelece uma esteira de estados sequencial, auditável e segura, mapeada diretamente nas regras de negócio codificadas no software:

[Colaborador: Bruno] ➡️ [Status: Aguard. Gerente] ➡️ [Status: Aguard. Cost Control] ➡️ [Status Final]
Criação do Pedido        Aprovação da Clara           Auditoria da Patrícia         Aprovado / Reprovado
(Formulário Completo)    (Comentário Opcional)        (Validação de WBS)            (Gera Logs/Criptografia)



### 🏛️ Mapeamento de Telas e Arquitetura do Sistema
O ecossistema materializa as interações corporativas através de um conjunto integrado de interfaces funcionais:
- **`login.png`**: Tela de autenticação baseada em perfis de acesso (Colaborador, Gerente e Cost Control) para controle estrito de rotas.
- **`homepage.png`**: Dashboard pessoal do solicitante contendo cartões dinâmicos de resumo de volumetria (Em andamento, Aprovadas, Reprovadas) e listagem de registros.
- **`tela de solicitação de viagem.png`**: Formulário de captura estruturada contendo campos de rota, período, seleção de Regime de Trabalho (Onshore/Offshore), Código WBS, Motivo da Viagem e checkboxes para serviços adicionais (Hotel e Aluguel de carro).
- **`tela de status da solicitação.png`**: Detalhamento do pedido com um stepper vertical de progresso em tempo real que garante total rastreabilidade do trâmite.
- **`fila de aprovações_tela do gerente.png`** e **`tela de aprovacao do gerente.png`**: Console gerencial da Clara para revisão de dados e inserção de despachos com comentários.
- **`tela de aprovacao do cost control.png`**: Interface financeira da analista Patrícia para auditoria do orçamento e encerramento do fluxo.
- **`tela de itens pendentes de aprovação pelo gerente.png`**: Tabela analítica gerencial cruzando status e tags coloridas padronizadas (amarelo, azul, verde, vermelho).

---

## 🔄 3. Espelhamento Metodológico: A Disciplina no Processo e no Produto
Este projeto adota o princípio do espelhamento metodológico: os conceitos de agilidade foram aplicados tanto na gestão do time quanto nas regras de comportamento do próprio software.

1. **A Disciplina no Processo (Gestão):** O MVP foi planejado sob o framework Scrum, limitando a capacidade técnica da equipe na Sprint 1 em 5 Story Points para garantir foco total nas entregas do core de captura de dados, mitigando riscos de estouro de cronograma.
2. **A Disciplina no Produto (Software):** O sistema atua como uma barreira ativa contra indisciplina financeira. A arquitetura de dados não permite a alteração de status para "Aprovado" sem passar sequencialmente pela validação do Cost Control, protegendo as chaves orçamentárias (WBS) da empresa contra compras não autorizadas.

---

## 🗺️ 4. O Workshop Lean Inception: Concepção em 9 Passos
O alinhamento estratégico do produto e a estruturação do MVP foram concebidos através de dinâmicas baseadas no framework de Paulo Caroli, documentadas no Miro:

* **Passo 1: Kickoff / Product Vision:** Alinhamento do propósito do SmartTravel focado em centralizar e agilizar o fluxo de solicitações e aprovações, garantindo governança e eficiência desde o primeiro dia.
* **Passo 2: É - Não É - Faz - Não Faz:** Delimitação técnica das fronteiras do sistema, isolando o escopo de emissão logística de outras ferramentas financeiras da empresa.
* **Passo 3: Product Goals:** Categorização das metas de negócio em eficiência (reduzir tempo de aprovação), processo (eliminar planilhas e e-mails) e compliance (100% de TRs auditadas).
* **Passo 4: Personas:** Detalhemento dos fatores humanos operantes (Bruno como viajante operacional e Clara como gestora aprovadora).
* **Passo 5: Users' Journeys:** Mapeamento das jornadas de criação e revisão condicional de viagens de última hora.
* **Passo 6: Feature Brainstorming:** Levantamento de funcionalidades utilizando post-its verde-água no Miro (Login, Formulário, Painel Gerencial, Validador do Cost Control).
* **Passo 7: Technical, Business and UX Review:** Matriz de trade-offs utilizando o gráfico semáforo para classificar esforço (E), valor de negócio ($) e UX (<3), dividindo os itens em tags de alta certeza (verde), média certeza (amarelo) e incerteza (vermelho).
* **Passo 8: Sequencer:** Organização incremental das ondas de valor respeitando os limites de esforço do Caroli:
  - *Onda 1 (MVP - Core):* Login, Formulário de Viagem e Dashboard Inicial.
  - *Onda 2 (MVP - Fluxo):* Painel Gerencial e Stepper de Status.
  - *Onda 3 (Incremento):* Painel de Cost Control e Tabela Analítica.
* **Passo 9: The MVP Canvas:** Consolidação estratégica em 7 blocos estruturados contendo propostas, personas, jornadas, funcionalidades do MVP, custos/cronograma, resultados esperados e métricas de validação.

---

## 🏗️ 5. Dinâmica do Product Backlog & Variação do Refinamento
O artefato `product-backlog.pdf` reflete fielmente o conceito real de **Backlog Emergente**. A variação no nível de detalhamento dos itens e a inclusão progressiva de novas histórias atende a uma justificativa metodológica clara:

As histórias mapeadas para a **Onda 1 e Onda 2 (Épicos 01 e 02)** encontram-se em estado de refinamento avançado, contendo especificações técnicas detalhadas, critérios BDD completos e checklists de DoR e DoD acoplados individualmente. Isso ocorre porque estes itens compõem o núcleo do MVP e o planejamento tático da Sprint imediata. Histórias ligadas ao incremento financeiro de **Onda 3 (Épico 03)** e integrações futuras possuem descrições mais enxutas, sendo refinadas progressivamente à medida que o pipeline de desenvolvimento se aproxima dessas fases, evitando o desperdício de esforço de design prematuro (Lean Requirements).

---

## 🗂️ 6. Estrutura de Arquivos do Repositório (Guia de Avaliação)
* **`/wireframe`**: Pasta contendo os layouts e arquivos de interface codificados (`login.png`, `homepage.png`, etc.).
* **`product-backlog.pdf`**: Documentação integral e legível de todos os Épicos, Features e Histórias de Usuário ordenados, contendo estimativas, prioridades, BDD e os checklists individuais de DoR e DoD limpos.
* **`sprint-backlog.pdf`**: Relatório tático focado nos itens selecionados para a Sprint 1, detalhando a alocação de capacidade do time para o primeiro incremento funcional do SmartTravel.
