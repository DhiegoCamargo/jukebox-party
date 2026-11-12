# Jukebox Party — piloto da Família Camargo

Projeto independente do Karaokê Play, usando o mesmo padrão: React + TypeScript + Vite, IFrame Player API, links e busca YouTube.

## Iniciar

1. Instale Node.js 20+.
2. Abra a pasta do projeto no terminal.
3. Execute `npm install` e `npm run dev`.
4. Acesse o endereço apresentado pelo Vite, normalmente `http://localhost:5173`.
5. Abra `/tv` (telão), `/pedir` (convidado) e `/admin` (controle) em **abas no mesmo navegador**.
6. PIN da demonstração: **1234**. Não use esse PIN em uma implantação pública.
7. Clique em **Iniciar Festa • Ativar Som** na tela `/tv` para liberar a reprodução.
8. Envie pedidos por links do YouTube, aprove fotos e veja a alternância no painel lateral.

## Busca no YouTube

Copie `.env.example` para `.env` e informe `VITE_YOUTUBE_API_KEY`. Restrinja a chave à origem autorizada e à YouTube Data API v3. A inclusão por URL funciona sem chave. A busca pode ter limite de cota; vídeos que proíbem incorporação podem falhar, mesmo após pesquisa.

## Importante: o que já funciona e o que ainda não está pronto

**Protótipo local:** layout responsivo TV e convidado, QR Code, identificação, fila, atualização entre abas do mesmo navegador, busca opcional, inclusão por URL, player do YouTube, avanço automático por evento do player, edição da fila, aprovação e exibição única de fotos, mural final salvo em HTML.

**Não apto para festa real com celulares distintos:** não há servidor de sincronização. `BroadcastChannel` e `localStorage` não conectam dispositivos diferentes; o QR Code aponta para o endereço da aplicação, mas não cria backend.

**Pendências antes de 21/11:** Firebase Realtime Database/Auth/Storage com regras seguras e transações, hospedar em HTTPS, administrar festas individuais, testar celular/TV em redes diferentes, autenticação segura, política de fotos, backup e limites de pedidos impostos pelo backend. O módulo de fotos no protótipo guarda imagens comprimidas em `localStorage` e tem limite de espaço; o álbum é arquivo HTML, não ZIP. O fluxo não persiste fotos entre dispositivos. O código atual é uma primeira versão para testar o visual e a experiência, não uma entrega de produção.

## Observações

- A tela de TV precisa de uma interação inicial do anfitrião por causa das políticas de autoplay.
- Em computadores com tela pequena, use o modo tela cheia do navegador para visualizar o telão.
- Não abra `/admin` em domínio público sem antes instalar autenticação real.
- Os arquivos originais do Karaokê Play não foram alterados.
