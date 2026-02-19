# Comparativo Técnico  
## SIGA vs Sistemas Legados Internos (Ex: Conecta)

---

## Visão Geral

Este documento apresenta um comparativo técnico entre o SIGA (Sistema Integrado de Gestão de Atendimentos) e sistemas legados internos tradicionalmente utilizados por cooperativas de crédito.

O objetivo é demonstrar diferenças arquiteturais, de segurança, governança e escalabilidade.

---

# 1. Arquitetura

| Critério | Sistemas Legados | SIGA |
|-----------|-----------------|------|
| Base tecnológica | Plataforma proprietária ou legado interno | Microsoft Power Platform |
| Banco de dados | Estrutura isolada ou customizada | Dataverse |
| Modelo arquitetural | Monolítico ou parcialmente modular | Modular (SIGA_Core + SIGA_Modulos) |
| Evolução tecnológica | Dependente do fornecedor original | Evolução controlada via Solution |
| Integração | Limitada ou via API customizada | Integração nativa com Microsoft 365 e Power BI |

---

# 2. Segurança

| Critério | Sistemas Legados | SIGA |
|-----------|-----------------|------|
| Controle de acesso | Perfil simples ou permissões fixas | Perfil + Setor + Módulo + Ação |
| Segurança estrutural | Customizada | Security Roles nativos do Dataverse |
| Isolamento de dados | Dependente da arquitetura interna | Isolamento completo por tenant |
| Controle em nível de registro | Nem sempre disponível | Nativo via Dataverse |
| Auditoria | Parcial ou inexistente | Auditoria nativa do Dataverse |

**Importante:**  
O SIGA utiliza segurança nativa do Dataverse como camada primária.  
A tabela `SIGA_Permissoes` controla apenas comportamento funcional da aplicação.

---

# 3. Governança

| Critério | Sistemas Legados | SIGA |
|-----------|-----------------|------|
| Separação entre operação e configuração | Geralmente inexistente | Separação obrigatória |
| Controle de alterações estruturais | Manual | Versionamento via Solution |
| Rastreabilidade | Limitada | Histórico estruturado por módulo |
| Gestão de permissões | Centralizada e rígida | Granular e parametrizável |

---

# 4. Escalabilidade

| Critério | Sistemas Legados | SIGA |
|-----------|-----------------|------|
| Modelo de dados | Estrutura rígida | Modelo híbrido estruturado |
| Expansão de módulos | Complexa e arriscada | Modular via SIGA_Modulos |
| Performance | Dependente da implementação | Baseada na infraestrutura Microsoft |
| Compatibilidade com BI | Limitada | Nativa com Power BI |

O SIGA evita estrutura EAV pura, utilizando modelo híbrido para garantir performance e facilitar relatórios.

---

# 5. Implantação

| Critério | Sistemas Legados | SIGA |
|-----------|-----------------|------|
| Instalação | Dependente de fornecedor | Importação de Solution Managed |
| Infraestrutura | Pode exigir servidor próprio | Utiliza o tenant Microsoft da cooperativa |
| Atualização | Manual e dependente | Controlada por versão de Solution |
| Customização | Alta dependência técnica | Configuração controlada dentro do padrão |

---

# 6. Modelo de Isolamento

O SIGA opera no tenant Microsoft da própria cooperativa, garantindo:

- Isolamento completo de dados
- Governança alinhada à política interna de TI
- Controle total pela própria instituição
- Ausência de dependência de infraestrutura externa

---

# Conclusão Técnica

O SIGA adota uma arquitetura moderna baseada em padrões Microsoft, com foco em:

- Segurança nativa
- Governança forte
- Escalabilidade controlada
- Evolução modular
- Isolamento por tenant

Em comparação com sistemas legados, o SIGA reduz risco tecnológico, melhora rastreabilidade e oferece maior alinhamento com a estratégia de transformação digital baseada no ecossistema Microsoft.

---

**SIGA – Plataforma de Governança Operacional**  
Desenvolvida sobre Microsoft Power Platform
