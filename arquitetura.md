# Arquitetura Técnica – SIGA
## Plataforma de Governança Operacional baseada em Microsoft Power Platform

---

## Visão Geral da Arquitetura

```mermaid
flowchart TB

    subgraph Tenant_Cooperativa["Tenant Microsoft da Cooperativa"]
    
        subgraph Dataverse["Dataverse"]
            Core["SIGA_Core\n(Tabelas Estruturais)"]
            Modulos["SIGA_Modulos\n(Tabelas de Negócio)"]
            Permissoes["SIGA_Permissoes\n(Controle Funcional)"]
        end

        subgraph Admin["Camada Administrativa"]
            ModelDriven["Model-Driven App\n(Administração)"]
        end

        subgraph Operacional["Camada Operacional"]
            Canvas["Canvas App\n(Usuários Finais)"]
        end

        Security["Security Roles\nBusiness Units\nTimes"]

    end

    ModelDriven --> Core
    ModelDriven --> Modulos
    ModelDriven --> Permissoes

    Canvas --> Modulos
    Canvas --> Permissoes

    Security --> Core
    Security --> Modulos
