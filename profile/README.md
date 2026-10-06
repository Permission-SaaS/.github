# Permission SaaS

Gerenciamento de permissões por API para projetos multi-tenant. Um cliente se cadastra, assina um
plano e recebe uma **ApiKey**. Com ela, os sistemas dele perguntam, em um único endpoint, se um cargo
pode acessar uma rota. Cada validação fica registrada numa trilha de auditoria.

É o projeto de longo prazo da Pós-Graduação de [Jairo Neto](https://github.com/JairoNetoDev): em vez de
um projeto novo por disciplina, cada uma evolui este mesmo sistema. As entregas ficam marcadas por tags
no repositório guarda-chuva.

## Repositórios

| Repositório | O que é |
| --- | --- |
| [`permission_saas`](https://github.com/Permission-SaaS/permission_saas) | Guarda-chuva: reúne os outros como submódulos, sobe o sistema inteiro com Docker Compose e guarda a arquitetura, as decisões (ADRs) e as entregas |
| [`permission_saas_api`](https://github.com/Permission-SaaS/permission_saas_api) | Aplicação principal: monolito modular com cadastro, planos, projetos e a validação de permissão |
| [`permission_saas_audit`](https://github.com/Permission-SaaS/permission_saas_audit) | Trilha de auditoria: serviço independente, com banco próprio, alimentado por fila no RabbitMQ |
| [`permission_saas_config`](https://github.com/Permission-SaaS/permission_saas_config) | Configuração centralizada (Spring Cloud Config Server) |
| [`permission_saas_front`](https://github.com/Permission-SaaS/permission_saas_front) | Front-end, ainda em definição |

## Rodar

```bash
git clone --recurse-submodules https://github.com/Permission-SaaS/permission_saas.git
cd permission_saas
cp .env.example .env
docker compose up -d --build
```

**Stack:** Java 21 · Spring Boot 4.1 · Spring Data JPA · PostgreSQL 16 · Flyway · Spring Modulith ·
Spring Cloud OpenFeign · Spring Cloud Config · RabbitMQ · Spring Batch · Docker Compose · Maven

## Licença

Todos os direitos reservados a Jairo Williams Guedes Lopes Neto. Os repositórios são públicos só para
consulta e avaliação; cada um tem o seu `LICENSE`. Para reportar uma falha de segurança, veja a
[política de segurança](https://github.com/Permission-SaaS/.github/blob/main/SECURITY.md).
