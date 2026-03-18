# Devops-cicd-pipeline

🚀 DevOps CI/CD Pipeline

Projeto demonstrando um pipeline completo de CI/CD utilizando Node.js, Docker e GitHub Actions.

📌 Objetivo

Este projeto foi criado para demonstrar habilidades práticas de DevOps, incluindo:

Integração Contínua (CI)

Entrega Contínua (CD)

Containerização com Docker

Automação de pipeline com GitHub Actions

🏗️ Arquitetura

Developer (git push)
        ↓

GitHub Actions (CI/CD)
        ↓

Run Tests (Jest)
        ↓

Build Docker Image
        ↓
        
Push to Docker Hub

🛠️ Tecnologias utilizadas

Node.js

Express

Docker

GitHub Actions

Jest (testes automatizados)

Supertest

📂 Estrutura do projeto
.
├── src/
│   └── app.js
├── test/
│   └── app.test.js
├── Dockerfile
├── package.json
└── .github/workflows/
    └── ci-cd.yml

⚙️ Pipeline CI/CD

A pipeline é executada automaticamente a cada push na branch main.

Etapas:

Checkout do código

Instalação de dependências

Execução de testes automatizados

Build da imagem Docker

Push da imagem para Docker Hub

🐳 Docker

Build da imagem
docker build -t devops .
Rodar container
docker run -p 3000:3000 devops

🧪 Testes

Executar testes localmente:

npm install
npm test

🔐 Variáveis de ambiente (GitHub Secrets)

Para funcionamento completo da pipeline:

DOCKER_USERNAME

DOCKER_PASSWORD

🚧 Deploy

O deploy via SSH foi configurado no pipeline, porém requer:

Servidor com Docker instalado

Acesso SSH configurado

Porta 22 liberada

Por padrão, essa etapa pode estar desabilitada para evitar falhas em ambientes sem servidor.

💡 Aprendizados

Durante o desenvolvimento deste projeto foram aplicados conceitos importantes de DevOps:

Automação de pipelines

Debug de erros em CI/CD

Gerenciamento de dependências

Containerização de aplicações

Integração com registries Docker

📈 Melhorias futuras

Deploy automático em cloud (AWS, Render, etc.)

Integração com Kubernetes

Monitoramento com Prometheus e Grafana

Versionamento de imagens Docker

Pipeline multi-stage

👨‍💻 Autor

Projeto desenvolvido como parte de estudos em DevOps.

⭐ Conclusão

Este projeto representa um fluxo real de CI/CD utilizado em ambientes profissionais, demonstrando desde testes automatizados até entrega de artefatos via Docker.