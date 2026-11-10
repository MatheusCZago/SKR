# Dashboard Gerencial SKR — instruções para o Claude

Idioma: português do Brasil (interface, textos, commits e respostas).

**Este repositório é público.** Nada de planilha real, token do CV CRM, dado de lead (nome, telefone, e-mail) ou nome completo de corretor aqui: a equipe aparece só por apelido.

## O que é

Painel gerencial da equipe de vendas do Evandro (SKR, imobiliária). O gerente solta a Planilha Base exportada do CV CRM e vê painel geral, corretores, empreendimentos, carteira de distribuição, alertas, histórico e relatório em texto. Tudo roda no navegador; a planilha não sai da máquina.

- `index.html`: o app inteiro (HTML, CSS e JS num arquivo, sem bibliotecas). Lê .xlsx com um leitor de zip/XML próprio e .csv.
- `sw.js` + `manifest.webmanifest` + ícones: app instalável (PWA) que abre sem internet. Ao mudar arquivos do cache, subir a versão de `CACHE` em `sw.js`.
- Publicado pelo GitHub Pages: https://matheusczago.github.io/SKR/ (1 a 2 minutos depois do push em `main`).

Esta é a V3. Existe uma V5 (demonstração do produto para vender a outras imobiliárias: login, várias empresas, tela Hoje, sugestão de distribuição, avisos, desempenho, conexão com o CV), toda simulada, que fica fora deste repositório, na máquina do usuário.

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
- Commit e push só com aprovação do usuário.
- Visual profissional, modo claro e escuro, azul-marinho da marca. A paleta roxo/amarelo foi descartada.

## Próximos passos conhecidos

- Juntar V3 e V5 numa base única; tirar equipe e nome da carteira de distribuição do código (virar configuração por empresa).
- Integração com o CV CRM (portal: https://desenvolvedor.cvcrm.com.br), que depende de token só leitura e autorização da SKR.
