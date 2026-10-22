# Chat em tempo real | Node.js + WebSocket

Projeto de comunicação em tempo real com interface web e servidor que distribui as mensagens aos clientes conectados.

## Como funciona
1. O participante informa um nome na interface.
2. O navegador abre uma conexão WebSocket.
3. O servidor recebe cada mensagem e a distribui aos clientes.
4. A interface diferencia mensagens próprias e mensagens de outros participantes.

O nome informado identifica a sessão na interface; não é uma autenticação de conta.

## Tecnologias
| Camada | Tecnologias |
| --- | --- |
| Interface | HTML, CSS e JavaScript |
| Servidor | Node.js e biblioteca `ws` |
| Configuração | `dotenv` |

## Requisitos
Node.js com npm. Para o comando de desenvolvimento com `--watch`, use uma versão compatível com esse recurso.

## Executar
```bash
git clone https://github.com/Yagog0/chat-websocket.git
cd chat-websocket/backend
npm ci
npm start
```

O servidor usa a porta `8080` por padrão. A variável `PORT` pode alterar a porta do servidor; nesse caso, atualize também a URL WebSocket da interface.

Em outro terminal, na raiz do repositório, com Python instalado:

```bash
python -m http.server 8000 --directory frontend
```

Abra `http://localhost:8000` em duas abas, informe nomes diferentes e teste a troca de mensagens.

A interface aponta atualmente para `ws://localhost:8080`. Para hospedar o projeto, configure o endereço do servidor e use `wss://` quando a página estiver em HTTPS. GitHub Pages sozinho não executa esse servidor Node.js.

## Estrutura
```text
backend/
  package.json
  package-lock.json
  src/server.js
frontend/
  index.html
  imagens/
```

Há também uma cópia da interface na raiz. Use `frontend/` como referência para o fluxo descrito acima.

## Estado atual
Protótipo para aprendizado. A interface renderiza conteúdo de mensagens com `innerHTML`; trate esse conteúdo antes de disponibilizar o chat para usuários externos. A integração atual não implementa persistência de mensagens ou controle de contas.

Desenvolvido por [Yago Maba](https://github.com/Yagog0).
