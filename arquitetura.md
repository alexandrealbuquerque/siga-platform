# Arquitetura Técnica – SIGA
## Plataforma de Governança Operacional baseada em Microsoft Power Platform

---

## Visão Geral da Arquitetura

```mermaid
flowchart TB

    subgraph Tenant_Cooperativa["Tenant Microsoft da Cooperativa"]
    
        subgraph Dataverse["Dataverse"]
            Core["SIGA_Core	(Tabelas Estruturais)"]
            Modulos["SIGA_Modulos	(Tabelas de Negócio)"]
            Permissoes["SIGA_Permissoes	(Controle Funcional)"]
        end

        subgraph Admin["Camada Administrativa"]
            ModelDriven["Model-Driven App	(Administração)"]
        end

        subgraph Operacional["Camada Operacional"]
            Canvas["Canvas App	(Usuários Finais)"]
        end

        Security["Security Roles	Business Units	Times"]

    end

    ModelDriven --> Core
    ModelDriven --> Modulos
    ModelDriven --> Permissoes

    Canvas --> Modulos
    Canvas --> Permissoes

    Security --> Core
    Security --> Modulos
