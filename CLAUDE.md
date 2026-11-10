# Dashboard Gerencial SKR — instruções para o Claude

Idioma: português do Brasil (interface, textos, commits e respostas).

**Este repositório é público.** Nada de planilha real, token do CV CRM, dado de lead (nome, telefone, e-mail) ou nome completo de corretor aqui: a equipe aparece só por apelido.

## O que é

Painel gerencial da equipe de vendas do Evandro (SKR, imobiliária). O gerente solta a Planilha Base exportada do CV CRM e vê painel geral, corretores, empreendimentos, carteira de distribuição, alertas, histórico e relatório em texto. Tudo roda no navegador; a planilha não sai da máquina.

- `index.html`: o app inteiro (HTML, CSS e JS num arquivo, sem bibliotecas). Lê .xlsx com um leitor de zip/XML próprio e .csv.
- `sw.js` + `manifest.webmanifest` + ícones: app instalável (PWA) que abre sem internet. Ao mudar arquivos do cache, subir a versão de `CACHE` em `sw.js`.
- Publicado pelo GitHub Pages: https://matheusczago.github.io/SKR/ (1 a 2 minutos depois do push em `main`).

Esta é a V3, que continua no ar para o Evandro. A V5 (demonstração simulada) foi arquivada. A **V6** (produto: conta com login, dados cifrados, leitura tolerante da planilha) está pronta e testada, mas o código fica **só na máquina do usuário** até ele decidir publicar. Decisões, funcionamento e pendências: [docs/V6.md](docs/V6.md). Leis e LGPD: [docs/LGPD-e-leis.md](docs/LGPD-e-leis.md).

## Regras de negócio (confirmadas pelo Evandro)

- Faixas de inatividade cumulativas pelo campo "Dias sem contato", critério estrito: acima de 15, 30 e 36 dias. O campo é provisório (a exportação não traz a data do último contato).
- Carteira de distribuição = leads do corretor "CORRETOR EQUIPE EVANDRO".
- Equipe padrão (apelidos): SERENA, LOYOLA, JOSUE, DORIVAL, SEABRA, NAIANY, NOVAES, RIPINA, LEONARDA, CALLERI, SENNA, CLAUDIA, FAUSTO, ALMADA, PIETRO. Quem não está na lista vira "Fora da equipe" e sai dos rankings.
- Triagem P1 a P4 da distribuição: P1 = Aguardando Atendimento ou Visita Realizada; P4 = dados completos (primeira interação e empreendimento) e até 15 dias; P3 = Tentativa de Contato com dados completos e mais de 15 dias; P2 = o restante. Sem aviso de "regra deduzida" na tela.
- Visitas e vendas são a situação atual do lead, não resultado do mês.
- Empreendimentos só com nomes oficiais: Chronos Pinheiros, Almá Pinheiros, Leaf Loefgren, Praça Higienópolis, Emiie Moema, Ayya Jardins, Latitude, Oliie 117, Lizz 177, BP Maestro Cardim e "Sem empreendimento". Siglas: CP, AP, LEAF, PH, EM, OLIIE, LIZZ, BP1. "Ch:ronos Pinheiros" = Chronos Pinheiros.
- Ficam de fora: Float By Yoo, Panorama Vila Romana e as siglas antigas ED, ED C, ED C C, ED C C C.
- Relatório sem ficha própria por corretor.

## Como trabalhar

- Ler o README e o `git log` antes de mexer.
- Editar `index.html`, testar abrindo no navegador (com uma planilha de teste fictícia, nunca a real), e só então commit.
- Commit e push só com aprovação do usuário. Desde 10/11/2026: **código não sobe** para o GitHub; anotações (docs, README, este arquivo) podem subir.
- Visual profissional, modo claro e escuro, azul-marinho da marca. A paleta roxo/amarelo foi descartada.

## Decisões em vigor (10/11/2026)

- **Sem integração direta com o CV CRM por enquanto**: o gerente exporta a planilha e arrasta para o painel. A integração pode voltar depois do lançamento, como atualização.
- O produto parte da V3 (não da V5). Equipe, carteira de distribuição e empreendimentos viraram configuração de cada conta (com um "modelo SKR").
- Dados do gerente ficam na conta dele, cifrados no navegador; só quem subiu vê. Sem servidor por enquanto.
- Mudanças na planilha não podem derrubar o app; a idade da planilha fica sempre visível.
- Tudo o que for acrescentado ou tirado é anotado em docs/V6.md.
