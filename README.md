# Dashboard Gerencial SKR

Painel gerencial da equipe do Evandro (SKR). Página única, sem servidor e sem dependências.

**Página:** https://matheusczago.github.io/SKR/ (disponível depois de ativar o GitHub Pages em Settings → Pages)

## Como usar

1. Abra a página.
2. Solte a Planilha Base exportada do CRM (`.xlsx` ou `.csv`).
3. Navegue pelas abas: Painel geral, Corretores, Empreendimentos, Distribuição, Alertas, Histórico e Relatório.

## O que cada aba mostra

- **Painel geral:** carteiras, situação dos leads, alertas de 15, 30 e 36 dias e qualidade dos dados.
- **Corretores:** tabela da equipe e ficha de cada corretor, com a lista de leads.
- **Empreendimentos:** leads, alertas e corretores de cada empreendimento. As siglas do CRM (CP, AP, PH, EM etc.) são somadas ao nome completo.
- **Distribuição:** leads sem corretor da equipe, com triagem P1 a P4.
- **Alertas:** lista de leads parados, com filtros e exportação.
- **Histórico:** cada exportação carregada fica guardada (só totais) para comparar semanas.
- **Relatório:** texto gerencial pronto para copiar.

## Privacidade

A planilha é lida no próprio navegador e não é enviada para a internet. Só os totais de cada exportação ficam guardados no navegador (aba Histórico). Nenhum nome, telefone ou e-mail de lead é guardado. **Não envie planilhas reais para este repositório.**

## Regras usadas

- Faixas de inatividade cumulativas, com o campo "Dias sem contato" do CRM: acima de 15, 30 e 36 dias. O campo é provisório, porque a exportação não traz a data do último contato.
- Carteira de distribuição: leads do corretor "CORRETOR EQUIPE EVANDRO".
- Triagem P1 a P4 (deduzida dos números do dashboard de 26/10/2026, a confirmar com o Evandro): P1 = Aguardando Atendimento ou Visita Realizada; P4 = dados completos e até 15 dias sem contato; P3 = Tentativa de Contato com dados completos; P2 = o restante.
- Visitas e vendas são a situação atual do lead, não o resultado do mês.

## Atualizar

Substitua o `index.html` por uma versão nova e faça o commit.
