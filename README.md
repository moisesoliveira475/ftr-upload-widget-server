# Upload Server

Este é o servidor backend para o widget de upload de imagens, desenvolvido durante o evento **FTR** da Rocketseat. O servidor lida com o upload de arquivos diretamente para o Cloudflare R2.

## 🚀 Tecnologias

- [Node.js](https://nodejs.org/)
- [Fastify](https://www.fastify.io/)
- [TypeScript](https://www.typescriptlang.org/)
- [Cloudflare R2](https://www.cloudflare.com/products/r2/) (via AWS SDK S3)
- [Zod](https://zod.dev/)
- [tsx](https://github.com/privatenumber/tsx)

## 🛠️ Instalação e Execução

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/rocketseat-education/ftr-upload-widget-server.git
   cd ftr-upload-widget-server
   ```

2. **Instale as dependências:**
   ```bash
   pnpm install
   ```

3. **Configure as variáveis de ambiente:**
   Copie o arquivo `.env.example` para `.env` e preencha com suas credenciais do Cloudflare R2.
   ```bash
   cp .env.example .env
   ```

4. **Inicie o servidor de desenvolvimento:**
   ```bash
   pnpm run dev
   ```
   O servidor estará rodando em `http://localhost:3333`.

## 📡 API Endpoints

### POST `/uploads`

Faz o upload de uma imagem para o storage.

- **Request Body**: `multipart/form-data` contendo o arquivo.
- **Limites**: Tamanho máximo de 4MB.
- **Resposta de Sucesso (201)**:
  ```json
  {
    "url": "https://pub-xxx.r2.dev/image-name.png"
  }
  ```

## ⚙️ Variáveis de Ambiente

O projeto utiliza as seguintes variáveis de ambiente:

- `CLOUDFLARE_ACCESS_KEY_ID`: ID da chave de acesso do Cloudflare R2.
- `CLOUDFLARE_SECRET_ACCESS_KEY`: Chave de acesso secreta do Cloudflare R2.
- `CLOUDFLARE_BUCKET`: Nome do bucket no Cloudflare R2.
- `CLOUDFLARE_ACCOUNT_ID`: ID da conta Cloudflare.
- `CLOUDFLARE_PUBLIC_URL`: URL pública do bucket R2.

---

Desenvolvido com ❤️ por Rocketseat.
