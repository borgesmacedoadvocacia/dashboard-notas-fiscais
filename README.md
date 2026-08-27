# Dashboard — Notas Fiscais

Controle de conformidade fiscal do escritório Borges Macedo Advocacia, alimentado em
tempo real pela planilha **"Notas Fiscais - BM Advocacia"** do Google Sheets.

**Acesso exclusivo das lideranças.** Só os perfis **Administração** e **Lideranças** têm
cofre neste painel.

## O que é exibido

| Seção | Conteúdo |
|---|---|
| Resumo Executivo | Valor recebido, valor com nota emitida, valor sem nota, conformidade fiscal, pendências acima de 90 dias, espera média, ticket médio e registros sem data. Filtro por ano do pagamento |
| Conformidade Fiscal | Valor por situação da nota (Lançada, Pendente, Lançar Depois, Dispensada) e distribuição da pendência por faixa de idade |
| Evolução Mensal | Valor recebido mês a mês empilhado por situação, com a linha de conformidade de cada mês |
| Onde Está a Pendência | Clientes com maior valor sem nota e distribuição por serviço contratado |
| Notas Fiscais | Tabela filtrável e pesquisável de todos os pagamentos. Clique numa linha para a ficha completa |
| Pontos de Atenção | Leitura executiva automática dos números |

## O que conta como regular

Só **Lançada** e **Dispensada** são consideradas regulares. **Pendente** e **Lançar
Depois** entram juntas como "sem nota emitida" — nos dois casos existe receita recebida
sem documento fiscal correspondente, que é o que importa para o risco.

A **conformidade fiscal** é calculada por **valor**, não por quantidade: uma nota de
R$ 50 mil pendente pesa mais que dez de R$ 500.

## Linhas em branco da planilha

A aba tem cerca de **340 linhas vazias pré-formatadas** em que a coluna de situação já
vem com "Pendente" por padrão, sem cliente nem valor. Elas **não** são notas devendo —
o painel as descarta e trabalha só com os pagamentos reais.

Os totais por situação batem exatamente com a tabela dinâmica da aba `Dados` da própria
planilha, o que confirma o recorte.

## Como funciona

- A aba é identificada por **gid**, não por nome — renomear a aba não quebra o painel.
- Leitura por nome de cabeçalho, com fallback pela letra da coluna.
- Atualização automática a cada 5 minutos. Arquivo único `index.html`, sem build.
