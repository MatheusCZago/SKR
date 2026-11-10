# LGPD e outras leis — mapa para o Painel Gerencial

Atualizado em 10/11/2026. **Não é parecer jurídico nem contábil.** É um mapa para conversar com advogado e contador, ligado ao que a V6 já faz. Itens marcados "confirmar" dependem deles.

## 1. Quem é quem (LGPD, Lei 13.709/2018)

| Papel | Quem | Por quê |
| --- | --- | --- |
| Titular | o lead (cliente da imobiliária) e o próprio usuário do painel | dono dos dados |
| Controladora (art. 5º, VI) | a imobiliária | decide por que e como usa os dados dos leads |
| Operador (art. 5º, VII e art. 39) | nós, **quando houver servidor** guardando os dados | trataria os dados em nome da imobiliária |
| Hoje (V6 sem servidor) | nós não recebemos nem temos acesso aos dados dos leads | tudo fica cifrado no aparelho do usuário |

- Base legal para os leads: definida e documentada pela imobiliária (normalmente procedimentos preliminares de contrato a pedido do titular ou legítimo interesse, art. 7º, V e IX).
- Base legal para a conta do usuário: execução do contrato de uso (art. 7º, V).
- Enquanto formos microempresa, valem as regras simplificadas para **agentes de pequeno porte** (Resolução CD/ANPD nº 2/2022): dispensa de indicar encarregado, desde que haja um **canal de comunicação** com titulares; prazos em dobro; registro simplificado. Não vale se o tratamento for de alto risco (confirmar).

## 2. O que a lei pede e como a V6 atende

| Exigência | Onde está na lei | Situação na V6 |
| --- | --- | --- |
| Segurança técnica | art. 46 | **Feito**: AES-GCM 256, PBKDF2 600 mil rodadas, senha mínima de 10 caracteres, trava após 5 erros, sessão encerra em 30 min, chave por conta, bloqueio de envio a outros endereços (CSP), nenhum serviço de terceiros |
| Necessidade e minimização | art. 6º, III | **Feito**: guarda só a última planilha (pode desligar) e um histórico de totais com os Ids dos leads parados há mais de 30 dias |
| Transparência | art. 6º, VI, e art. 9º | **Rascunho**: Política de Privacidade, Termos de Uso e "Como protegemos seus dados" dentro do app. Falta revisão jurídica e dados da empresa |
| Direitos do titular (acesso, portabilidade, eliminação) | art. 18 | **Feito para o usuário**: baixar meus dados, apagar planilha/histórico, apagar conta. Leads: atendidos pela imobiliária |
| Registro das operações | art. 37 | **Parcial**: registro de atividades cifrado por conta. Falta o registro (inventário) do próprio fornecedor |
| Comunicação de incidente | art. 48 e Resolução CD/ANPD nº 15/2024 | **Texto na Política** (3 dias úteis). Falta o procedimento interno (seção 6) |
| Encarregado ou canal | art. 41, Res. 2/2022 e Res. 18/2024 | **Falta**: definir o e-mail de contato e, se preciso, o encarregado |
| Contrato com a imobiliária (operador) | art. 39 | **Falta**: só necessário quando houver servidor (seção 4) |
| Cookies e armazenamento | Guia de cookies da ANPD (2022) | **Ok**: só armazenamento estritamente necessário (conta e dados cifrados); sem rastreamento, então sem banner de cookies |

Sanções da LGPD: advertência, multa de até 2% do faturamento (limitada a R$ 50 milhões por infração), publicização, bloqueio ou eliminação dos dados (art. 52; dosimetria na Resolução CD/ANPD nº 4/2023).

## 3. Hospedagem das páginas

- Hoje as páginas ficam no **GitHub Pages (EUA)**. Os arquivos do app não levam dados, e a V6 não envia nada ao GitHub (testado), mas o GitHub, como hospedagem, registra o endereço IP de quem acessa. Citar isso na Política quando publicar, ou mudar para hospedagem no Brasil.

## 4. Quando houver servidor (sincronizar entre aparelhos)

- **Continuar cifrando no navegador** antes de enviar: o servidor guarda só conteúdo ilegível e nunca recebe a senha. O formato do cofre da V6 já é esse.
- **Marco Civil da Internet (Lei 12.965/2014), art. 15**: empresa que mantém aplicação de internet com fins econômicos deve guardar os **registros de acesso à aplicação por 6 meses**, sob sigilo e em ambiente seguro.
- **Contrato de tratamento de dados (operador)** com cada imobiliária: finalidade, instruções, sigilo, segurança, suboperadores (hospedagem), aviso de incidente, devolução ou eliminação ao fim do contrato, auditoria.
- **Transferência internacional** (art. 33 e Resolução CD/ANPD nº 19/2024): servidor fora do Brasil exige cláusulas-padrão ou outro mecanismo. Mais simples: região São Paulo do provedor.
- Mesmo cifrados, tratar os dados como pessoais (mais seguro; confirmar com advogado).
- Avaliar **Relatório de Impacto (RIPD)**, art. 38, se a ANPD pedir ou se o tratamento for de alto risco.

## 5. Outras leis e registros

| Assunto | Norma | O que fazer | Situação |
| --- | --- | --- | --- |
| Venda pela internet | Código de Defesa do Consumidor (Lei 8.078/1990) e Decreto 7.962/2013 | Mostrar no site nome empresarial, CNPJ, endereço e contato; contrato claro; atendimento eletrônico. Imobiliária pequena pode ser vista como consumidora: arrependimento em 7 dias (art. 49) se contratar pelo site (confirmar) | falta |
| Contrato assinado online | Lei 14.063/2020 e MP 2.200-2/2001 | Aceite eletrônico com registro (data, versão, conta) | aceite com versão e data já gravado na conta |
| Software | Lei 9.609/1998 | Proteção automática por direito autoral; registro no INPI é opcional e ajuda a provar autoria | falta decidir |
| Marca | Lei 9.279/1996 | Pesquisar e registrar a marca no INPI (classes de software/serviços online, ex.: 9 e 42) antes de divulgar | falta |
| Domínio | Registro.br | `.com.br` exige CPF ou CNPJ; registrar em nome da empresa | falta |
| Acessibilidade | Lei 13.146/2015 (LBI), art. 63 | Site acessível (contraste, teclado, leitores de tela) | parcial: contraste, foco visível e rótulos já existem; falta auditoria |
| Avisos por WhatsApp (futuro) | Política do WhatsApp Business + LGPD | Opt-in de quem recebe, modelos aprovados | futuro |

## 6. Procedimento de incidente (a escrever com o advogado)

1. Conter (desligar acesso, trocar chaves de servidor, preservar registros).
2. Avaliar risco: que dados, quantos titulares, estavam cifrados?
3. Avisar a imobiliária (controladora) imediatamente.
4. Se houver risco ou dano relevante: comunicação à ANPD e aos titulares em **3 dias úteis** (Res. 15/2024), com o conteúdo mínimo do regulamento.
5. Registrar tudo e guardar por pelo menos 5 anos (Res. 15/2024, confirmar).

Na V6 sem servidor, o cenário mais provável é o usuário perder o aparelho: os dados estão cifrados pela senha dele.

## 7. Empresa e impostos (confirmar com o contador)

- **Microempresa (ME)**, não MEI: as atividades de software não estão entre as permitidas ao MEI.
- **CNAE**: 6203-1/00 (licenciamento de programas não customizáveis) ou 6311-9/00 (provedores de aplicação e hospedagem), conforme o modelo de venda.
- **ISS** (LC 116/2003): item 1.05 (licenciamento de uso de software) ou 1.03 (processamento e hospedagem de sistemas).
- **Simples Nacional**: Anexo III ou V, conforme o "fator R" (folha de pagamento ÷ faturamento).
- **Nota fiscal de serviço (NFS-e)**: com a reforma tributária (Emenda 132/2023 e LC 214/2025), as notas estão migrando para o padrão nacional e passam a informar CBS e IBS, com 2026 como ano de teste. Ver com o contador como fica no município da empresa.
- **Termos e Política** só valem de verdade com os dados da empresa preenchidos (CNPJ, endereço, contato).

## 8. Próximos passos sugeridos

1. Abrir a empresa (ME) e definir CNAE com o contador.
2. Pesquisar e registrar a marca e o domínio.
3. Advogado revisar Política, Termos e o futuro contrato de operador, e definir o canal de contato com titulares.
4. Escrever o inventário de tratamento do fornecedor e o procedimento de incidente.
5. Só depois disso: oferecer o piloto pago a outras imobiliárias.
