# RecMoney

Plataforma onde as pessoas gravam tarefas do dia a dia com o celular preso na testa e recebem via Pix por vídeo aprovado. Os vídeos viram dados para treinar robôs e IA.

## Arquivos

- `index.html`: o site inteiro (HTML, CSS, JavaScript, ícones e ícone do navegador)
- `img/missoes/`: fotos das missões, uma por missão (`<id>.jpg`). A lista completa com os nomes está no `LEIA-ME.md` da pasta.
- `premium/index.html`: atalho para `recmoney.site/premium`. Sem chave, abre a página de venda do Premium. Com a chave de entrega (`?k=...`) ou um link individual (`?t=...`), ativa o Premium na conta.

A chave do link fixo e o gerador de links individuais **não** ficam no repositório. O `index.html` guarda só o hash da chave, então ver o código não revela o link.

## Como rodar

- **No computador:** abra o `index.html` no navegador.
- **No GitHub Pages:** em Settings → Pages, escolha a branch `main` e salve. O site fica em `seuusuario.github.io/recmoney`.

As fontes (Bricolage Grotesque, Onest e JetBrains Mono) vêm do Google Fonts, então é preciso internet.

## O que tem

- Tela de entrada com apresentação, cadastro e login
- Missões grátis e Premium, com valor, tempo, XP e vagas
- Gravação pela câmera do celular ou envio de vídeo
- Envios, ranking, convites, conquistas e carteira com saque via Pix
- Modo claro e noturno, pensado primeiro para celular

## Limitações atuais

Esta versão roda só no navegador, sem servidor:

- Login, saldo e missões ficam salvos no `localStorage` de cada aparelho
- A senha não é conferida
- A aprovação dos vídeos é simulada (cerca de 45 segundos)
- O Premium é ativado por link assinado digitalmente e ligado ao e-mail do comprador. Links falsos ou editados são recusados, e marcar o Premium na mão no navegador não funciona. Ainda assim, sem servidor, quem alterar o código do site consegue burlar.
- Para cancelar um link (reembolso ou chargeback), coloque o ID dele na lista `REVOKED` do `index.html`
- O Pix não está ligado a pagamento real

Para virar produção, é preciso um servidor com banco de dados, autenticação, armazenamento dos vídeos, revisão de verdade e integração com Pix.
