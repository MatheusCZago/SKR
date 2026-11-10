# Dashboard Gerencial SKR

Painel gerencial da equipe do Evandro (SKR). Página única, sem servidor e sem dependências.

**Página:** https://matheusczago.github.io/SKR/ (no ar pelo GitHub Pages)

**Próxima versão (V6):** em desenvolvimento, ainda não publicada. Conta com login, dados cifrados no navegador e leitura tolerante a mudanças na planilha. Anotações em [docs/V6.md](docs/V6.md) e [docs/LGPD-e-leis.md](docs/LGPD-e-leis.md).

## Como usar

1. Abra a página.
2. Solte a Planilha Base exportada do CRM (`.xlsx` ou `.csv`). Ela fica guardada neste navegador e carrega sozinha da próxima vez.
3. Navegue pelas abas: Painel geral, Corretores, Empreendimentos, Distribuição, Alertas, Histórico e Relatório.

## O que cada aba mostra

- **Painel geral:** carteiras, situação dos leads, alertas de 15, 30 e 36 dias e qualidade dos dados.
- **Corretores:** tabela da equipe e ficha de cada corretor, com a lista de leads.
- **Empreendimentos:** leads, alertas e corretores de cada empreendimento. As siglas do CRM (CP, AP, PH, EM etc.) são somadas ao nome completo.
- **Distribuição:** leads sem corretor da equipe, com triagem P1 a P4.
- **Alertas:** lista de leads parados, com filtros e exportação.
- **Histórico:** cada exportação carregada fica guardada (só totais) para comparar semanas.
- **Relatório:** texto gerencial pronto para copiar.

## Instalar como aplicativo

Com a página aberta pelo endereço do GitHub Pages (https):

- **Computador (Chrome ou Edge):** clique no ícone de instalar na barra de endereço, ou em ⋮ → Salvar e compartilhar → Instalar página como app.
- **Android (Chrome):** ⋮ → Instalar app (ou Adicionar à tela inicial).
- **iPhone (Safari):** botão Compartilhar → Adicionar à Tela de Início.

Depois de instalado, abre em janela própria e funciona sem internet.

## Privacidade

- A planilha é lida no próprio navegador e **não é enviada para a internet**.
- A última planilha fica guardada neste navegador (inclui nome, telefone e e-mail dos leads), para carregar sozinha quando a página for reaberta. Dá para desligar ou apagar em Configurações → Planilha guardada.
- Cada exportação também deixa seus totais no histórico (sem dados pessoais).
- **Não envie planilhas reais para este repositório.** Ele é público.
- Tudo fica guardado por navegador e por endereço: outro computador, outro navegador ou o app do iPhone começam vazios.

## Regras usadas

- Faixas de inatividade cumulativas, com o campo "Dias sem contato" do CRM: acima de 15, 30 e 36 dias. O campo é provisório, porque a exportação não traz a data do último contato.
- Carteira de distribuição: leads do corretor "CORRETOR EQUIPE EVANDRO".
- Triagem P1 a P4: P1 = Aguardando Atendimento ou Visita Realizada; P4 = dados completos e até 15 dias sem contato; P3 = Tentativa de Contato com dados completos; P2 = o restante.
- Visitas e vendas são a situação atual do lead, não o resultado do mês.

## Atualizar

Substitua o `index.html` por uma versão nova e faça o commit. O GitHub Pages publica sozinho em 1 a 2 minutos, e o app instalado se atualiza na próxima abertura.
