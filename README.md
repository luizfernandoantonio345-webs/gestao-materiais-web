<div align="center">

# GWI Materiais — Frontend

**Interface web e mobile do sistema de almoxarifado da GRAMO Engenharia**

![React](https://img.shields.io/badge/React_19-20232A?logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-instalável-5A0FC8?logo=pwa&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-tempo_real-22D3A6)

[**Abrir demo**](https://gwi-frontend.vercel.app) · [API (FastAPI)](https://github.com/luizfernandoantonio345-webs/gwi-materiais-backend)

</div>

---

SPA responsiva (desktop e celular), instalável como PWA, feita para o almoxarifado e o canteiro de obra.
O almoxarife dá baixa de material lendo o QR do crachá do colaborador direto pela câmera do celular.

## Tecnologias

- **React 19** + **Vite**
- Design system próprio (tema escuro industrial) — sem framework de CSS
- `lucide-react` (ícones), `qrcode.react` (geração de QR), `html5-qrcode` (leitura de QR)
- Notificações em tempo real via **WebSocket** (com atualização periódica como fallback)

## Funcionalidades

- Autenticação com JWT + refresh automático; MFA (TOTP) opcional por usuário
- Perfis de acesso: Almoxarife, ADM/Compras e Gerente
- Baixa de materiais por QR Code (crachá do colaborador e código do material)
- Pedidos, aprovações por alçada, fila de compras e entrada de estoque
- Comodato de ferramentas (retirada e devolução)
- Solicitações de reposição de estoque
- Cadastro e **importação por planilha** (`.xlsx`/`.csv`) de materiais e colaboradores
- Geração e impressão de QR Code para colaboradores e ferramentas
- Notificações em tempo real com aviso visual e sonoro

## Executando localmente

```bash
npm install
npm run dev
```

Configure a URL da API pela variável de ambiente `VITE_API_BASE` (padrão: `http://localhost:8000`).

## Scripts

| Comando | Descrição |
|---|---|
| `npm run dev` | Ambiente de desenvolvimento |
| `npm run build` | Build de produção |
| `npm run preview` | Pré-visualização do build |
| `npm run lint` | Análise estática (oxlint) |

## Estrutura

```
src/
  api/         cliente HTTP + WebSocket
  components/  componentes reutilizáveis
  hooks/       hooks (dados, responsividade, toasts)
  layout/      sidebar, topbar, navegação mobile
  pages/       telas por funcionalidade
  styles/      tokens de tema
  utils/       formatação, perfil, som
```

## Deploy

Publicado como site estático (build do Vite). A URL da API é definida por `VITE_API_BASE`
no ambiente de build. O deploy é automático a cada push na branch `master`.

## Licença

Uso interno — GRAMO Engenharia. Todos os direitos reservados.
