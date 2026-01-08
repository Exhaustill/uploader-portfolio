# Private File Uploader - Fullstack & Cloud Storage

Um sistema de upload de arquivos de alta performance, focado em privacidade e segurança, utilizando armazenamento em nuvem (Cloudflare R2).

## O projeto
Este projeto foi desenvolvido para resolver o desafio de transferir arquivos de forma rápida e segura, com um ciclo de vida controlado (auto-delete). Diferente de outras soluções, este uploader prioriza a privacidade do usuário: as informações sobre os arquivos enviados ficam gravadas apenas no navegador do usuário (LocalStorage), e os arquivos são deletados permanentemente do servidor após 30 minutos.

**Link do projeto no ar:** [https://exhaustill-uploader.vercel.app/](https://exhaustill-uploader.vercel.app/)

## Tecnologias Utilizadas

### Frontend
- **Framework:** Next.js (App Router)
- **Biblioteca:** React 19
- **Estilização:** Tailwind CSS (Modern Dark Mode)
- **Lógica:** TypeScript & Real-time Progress Tracking (XMLHttpRequest API)

### Backend
- **Ambiente:** Node.js
- **API Framework:** Express.js
- **Storage Integration:** AWS SDK (S3 Client)
- **File Management:** Multer & Multer-S3

### Infraestrutura & Cloud
- **Armazenamento:** Cloudflare R2 (Object Storage)
- **Hospedagem Front:** Vercel
- **Hospedagem Back:** Render

---

## Desafios Técnicos Superados

### 1. Integração com Object Storage (S3/R2)
Implementação de um pipeline de upload via stream para o Cloudflare R2, garantindo que arquivos grandes (até 500MB) sejam processados de forma eficiente pelo servidor Node.js sem sobrecarga de memória.

### 2. Monitoramento de Progresso em Tempo Real
Superação das limitações da fetch API para rastreio de upload, utilizando a XMLHttpRequest API para fornecer um feedback visual preciso (barra de progresso) para o usuário final.

### 3. Ciclo de Vida e Limpeza de Dados
Criação de uma rotina automatizada (setInterval) no servidor para monitorar o tempo de vida dos arquivos e realizar a exclusão física no R2 após 30 minutos, garantindo que o servidor não acumule dados desnecessários.

### 4. Segurança e Filtros
Implementação de validações rigorosas de extensões de arquivos (bloqueio de .exe, .bat, .js, etc) e limites de tamanho para prevenir abusos no armazenamento.

---

## Contato
Se você tem interesse em saber mais sobre a arquitetura deste projeto ou quer bater um papo sobre desenvolvimento Fullstack, sinta-se à vontade para se conectar comigo!

---
*Nota: O código-fonte deste projeto é mantido em um repositório privado por questões de segurança e boas práticas de infraestrutura.*
