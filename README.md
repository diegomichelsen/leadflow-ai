# LeadFlow AI

> Plataforma de automação do ciclo de captação, qualificação e encaminhamento de leads.

**Status:** Planejamento  
**Versão:** 0.1  
**Categoria:** Automação comercial, CRM e integrações

## 1. Visão geral

O LeadFlow AI pretende automatizar o fluxo entre a entrada de um lead e seu encaminhamento para o processo comercial adequado.

A solução combinará APIs, webhooks, validação de dados, regras comerciais e, quando houver benefício comprovável, inteligência artificial para apoiar a classificação de mensagens.

## 2. Problema de negócio

Leads recebidos de diferentes canais podem apresentar dados incompletos, duplicidades ou falta de acompanhamento. A ausência de integração entre formulários, marketing e CRM aumenta o trabalho manual e dificulta rastrear o que aconteceu com cada oportunidade.

## 3. Objetivos

- Centralizar a entrada de leads.
- Validar e normalizar informações.
- Evitar duplicidades.
- Aplicar critérios documentados de qualificação.
- Encaminhar oportunidades aos destinos corretos.
- Automatizar tarefas de acompanhamento.
- Registrar o histórico de processamento.
- Medir o desempenho do fluxo.

## 4. Escopo funcional previsto

### Captura e validação

- Receber registros por API, formulário ou webhook.
- Validar campos obrigatórios e formatos.
- Normalizar e-mails, telefones e outros atributos.
- Rejeitar ou colocar em análise registros inválidos.
- Registrar a origem e o horário de recebimento.

### Deduplicação e qualificação

- Detectar possíveis duplicidades usando critérios definidos.
- Diferenciar duplicidade confirmada de correspondência incerta.
- Aplicar regras de qualificação configuráveis.
- Utilizar IA opcionalmente para classificar necessidades descritas em texto.
- Registrar os critérios utilizados para cada encaminhamento.

### Integração comercial

- Encaminhar leads a um CRM simulado ou compatível.
- Atualizar status e informações.
- Automatizar notificações e tarefas de acompanhamento.
- Tratar falhas e respostas inesperadas da integração.
- Permitir reprocessamento sem criar registros duplicados.

### Indicadores

- Leads recebidos e validados.
- Registros duplicados ou rejeitados.
- Distribuição por canal e categoria.
- Tempo entre recebimento e encaminhamento.
- Falhas e execuções recuperadas.

## 5. Arquitetura prevista

- **n8n:** orquestração dos fluxos.
- **Python e FastAPI:** validação e regras customizadas.
- **APIs REST e webhooks:** comunicação entre componentes.
- **PostgreSQL:** persistência e histórico, caso necessário ao desenho final.
- **IA:** classificação assistida de texto, se validada.
- **Docker Compose:** execução local.
- **Pytest:** testes.

## 6. Regras de confiabilidade

- Validar os dados antes de enviá-los ao CRM.
- Definir uma estratégia explícita de deduplicação.
- Utilizar chaves de idempotência quando aplicável.
- Implementar retentativas limitadas.
- Registrar erros e identificadores de execução.
- Evitar comunicações duplicadas.
- Respeitar consentimento, finalidade e minimização de dados em cenários que simulem dados pessoais.

## 7. Testes e critérios de aceitação

A primeira versão deverá demonstrar:

1. Recebimento de um lead válido.
2. Rejeição ou tratamento de entradas inválidas.
3. Detecção de duplicidades.
4. Aplicação correta das regras de qualificação.
5. Encaminhamento ao CRM simulado.
6. Tratamento de falhas e reprocessamento seguro.
7. Histórico consultável de cada operação.
8. Testes automatizados dos cenários principais.

## 8. Dados

Serão utilizados leads fictícios, com canais, categorias e status comerciais simulados. Nenhum contato real será necessário.

## 9. Próximos passos

1. Definir o processo comercial demonstrado.
2. Documentar regras de qualificação e deduplicação.
3. Criar exemplos de entrada e resultados esperados.
4. Implementar a captura e a validação.
5. Integrar o CRM simulado.
6. Implementar acompanhamento, testes e indicadores.

## 10. Limitações

A qualificação automatizada será um apoio ao processo comercial, não uma garantia de conversão. O uso de IA dependerá de critérios verificáveis e de testes com exemplos representativos.