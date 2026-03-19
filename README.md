## DevOps CI/CD Pipeline com Node.js, Docker e GitHub Actions

Este repositório demonstra um projeto prático de **CI/CD** aplicado a uma API simples em Node.js, com foco em boas práticas de automação para entrega contínua.

A proposta é servir como portfólio técnico para mostrar:
- como estruturar uma aplicação mínima para testes e deploy;
- como automatizar validações com GitHub Actions;
- como versionar, buildar e publicar imagem Docker para distribuição.

---

## Visão Geral do Projeto

O projeto expõe um endpoint HTTP com Express:
- `GET /` -> retorna `{"message":"Hello WORLD!!"}`

Mesmo sendo uma API simples, ele foi desenhado para demonstrar um fluxo DevOps real:
- código versionado no GitHub;
- testes automatizados com Jest + Supertest;
- pipeline CI/CD no GitHub Actions;
- build e push de imagem Docker para Docker Hub.

---

## Objetivo (Portfólio)

Este projeto é ideal para demonstrar competências em:
- Node.js para backend básico;
- testes automatizados de API;
- conteinerização com Docker;
- automação de integração e entrega contínua (CI/CD);
- uso de secrets no GitHub Actions para autenticação segura.

---

## Arquitetura e Estrutura

Estrutura principal:

```text
.
├── .github/workflows/ci-cd.yml   # Pipeline CI/CD
├── src/app.js                    # App Express (rotas)
├── server.js                     # Inicialização do servidor
├── test/app.test.js              # Testes automatizados
├── Dockerfile                    # Imagem da aplicação
├── package.json                  # Scripts e dependências
└── README.md
```

Fluxo resumido:
1. Desenvolvedor envia código para `main`.
2. GitHub Actions instala dependências e roda testes.
3. Pipeline faz build da imagem Docker.
4. Pipeline publica a imagem no Docker Hub.
5. (Opcional) etapa de deploy via SSH pode ser ativada.

---

## Tecnologias Utilizadas

- **Node.js 18**
- **Express**
- **Jest**
- **Supertest**
- **Docker**
- **GitHub Actions**

---

## Onde este projeto é usado

Este projeto pode ser usado como:
- template inicial para pipelines DevOps de APIs Node.js;
- laboratório para estudar CI/CD na prática;
- base para entrevistas técnicas e apresentação de portfólio;
- ponto de partida para evoluir para ambientes de staging/produção.

---

## Pré-requisitos

Para rodar localmente, instale:

- [Node.js 18+](https://nodejs.org/)
- [npm](https://www.npmjs.com/) (já vem com Node.js)
- [Docker](https://www.docker.com/) (opcional, para execução em container)
- [Git](https://git-scm.com/)

---

## Como Executar Localmente (sem Docker)

1. Clone o repositório:

```bash
git clone <URL_DO_REPOSITORIO>
cd Devops-cicd-pipeline
```

2. Instale as dependências:

```bash
npm install
```

3. Execute os testes:

```bash
npm test
```

4. Inicie a aplicação:

```bash
npm start
```

5. Acesse no navegador ou via curl:

- URL: `http://localhost:3000/`
- Exemplo:

```bash
curl http://localhost:3000/
```

Resposta esperada:

```json
{"message":"Hello WORLD!!"}
```

---

## Como Executar com Docker

1. Build da imagem:

```bash
docker build -t devops-cicd-pipeline:latest .
```

2. Rodar container:

```bash
docker run -d -p 3000:3000 --name devops-app devops-cicd-pipeline:latest
```

3. Testar endpoint:

```bash
curl http://localhost:3000/
```

4. Parar e remover container:

```bash
docker stop devops-app && docker rm devops-app
```

---

## Pipeline CI/CD (GitHub Actions)

Arquivo: `.github/workflows/ci-cd.yml`

A pipeline é acionada em push na branch `main` e executa:
1. Checkout do código
2. Setup do Node 18
3. Instalação de dependências
4. Execução de testes
5. Build da imagem Docker
6. Login no Docker Hub (via secrets)
7. Push da imagem

### Secrets necessários no GitHub

Configure no repositório:
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

Para habilitar deploy remoto (se desejar), também seriam necessários:
- `SERVER_HOST`
- `SSH_KEY`

---

## Melhorias Futuras

- adicionar versionamento semântico de imagens (`v1.0.0`, `latest`);
- incluir lint e análise de qualidade no pipeline;
- ativar deploy automático em VPS/Kubernetes;
- adicionar endpoint de health check (`/health`);
- criar variáveis de ambiente com `.env`.

---

## Autor

Projeto desenvolvido por **Johnny Max** como estudo e demonstração de práticas de **DevOps + CI/CD** aplicadas a aplicações Node.js.
