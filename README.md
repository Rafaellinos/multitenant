# multi-tenant

- Usado para multiplos clientes na mesma aplicação e infra
- Muito usado com SaaS
- Ou multi-tenancy
- exemplos:
  - google workspace
  - salesforce
  - shopify
  - AWS contas

## Como classificar um tenant?

- portais de franquias, redes de clinicas, redes de escolas
- Acima, cada tenant pode ser filiais, grupos

## multi-tenancy vs multi-instance

- Multi instance:
  - Cada aplicação tem sua propria instancia, 10 cliente == 10 aplicações
  - Pode ser docker instance, maquinas virtuais na mesma maquina

- Multi tenant
  - unica aplicação
  - As vezes, mesmo banco de dados
  - isolamento lógico (eg schema)

| aspecto        | multi-instance | multi-tenant |
|----------------|----------------|--------------|
| custo          | alto           | baixo        |
| isolamento     | fisico         | logico       |
| escalabilidade | limitada       | alta         |
| deploy         | separado       | centralizado |

| situacao                                 | recomendado               |
|------------------------------------------|---------------------------|
| regulatorios                             | multi instance            |
| plugin exclusivos por cliente            | multi instance            |
| Sas milhares pequenos/medios             | multi tenant              |
| foco em reduzir custo                    | multi tenant              |
| deploy/manutencao simples                | multi tenant              |
| clientes enterprise demandas especificas | hibrido ou multi instance |

- Vantagens
  - economia infra
  - deploys centralizados
  - governança unificados

- Desvantagens
  - isolamento de dados precisa ser rigoroso
  - performance varia entre tenants
  - customização por clientes precisam de arquitetuas flexíveis
  - debug precisa ser rastreável por tenant (saber qual cliente)
  - bug podem afetar todos os clientes
