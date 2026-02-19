# Perguntas Difíceis da TI
## SIGA – Plataforma de Governança Operacional

Este documento antecipa questionamentos técnicos comuns de equipes de TI em cooperativas de crédito.

---

# 1. Onde ficam os dados?

Os dados ficam exclusivamente no **tenant Microsoft da própria cooperativa**, armazenados no **Dataverse**.

O SIGA não utiliza banco externo, servidor próprio ou infraestrutura paralela.

---

# 2. Existe risco de vazamento entre cooperativas?

Não.

Cada cooperativa opera em seu próprio tenant Microsoft.

Não existe base central compartilhada.
Não existe multi-tenant no modelo atual.
Não há comunicação entre ambientes.

---

# 3. A segurança é customizada ou nativa?

A segurança estrutural é **100% nativa do Dataverse**, utilizando:

- Security Roles
- Business Units
- Times
- Controle em nível de registro

A tabela `SIGA_Permissoes` controla apenas comportamento funcional da aplicação.

---

# 4. É possível que um usuário acesse dados indevidamente via API?

Não.

Como a segurança é aplicada no nível do Dataverse, qualquer acesso via API respeita os mesmos Security Roles.

Não há segurança implementada apenas na interface.

---

# 5. Como funciona a atualização da plataforma?

O SIGA é entregue via **Solution Managed**.

Atualizações são feitas por:
- Nova versão da Solution
- Importação controlada
- Versionamento estruturado

O núcleo estrutural não pode ser alterado pela cooperativa.

---

# 6. Como evitar customizações descontroladas?

O modelo do SIGA é dividido em:

- SIGA_Core (núcleo protegido)
- SIGA_Modulos (camada extensível)

A cooperativa pode configurar dentro do padrão, mas não alterar a arquitetura base.

---

# 7. O modelo meta-driven não compromete performance?

Não.

O SIGA utiliza modelo híbrido, evitando estrutura EAV pura.

- Estrutura estável usa tabelas reais
- Campos adicionais usam JSON controlado
- Permissões são cacheadas em sessão

---

# 8. É compatível com Power BI?

Sim.

Os dados estão no Dataverse, permitindo:
- Conexão direta ao Power BI
- Modelagem analítica estruturada
- Relatórios executivos

---

# 9. Existe dependência de conectores premium externos?

Não.

O SIGA foi projetado para operar exclusivamente dentro do ecossistema Microsoft Power Platform.

---

# 10. O que acontece se a cooperativa encerrar contrato?

Como o sistema opera no próprio tenant da cooperativa:

- Os dados permanecem no ambiente da instituição
- A cooperativa mantém controle total sobre sua base
- Não há retenção externa de dados

---

# 11. Como o SIGA se posiciona frente a sistemas legados?

O SIGA:

- Utiliza arquitetura moderna baseada em Dataverse
- Implementa governança real
- Permite evolução modular
- Reduz risco tecnológico
- Elimina dependência estrutural de fornecedor proprietário

---

# Conclusão Técnica

O SIGA foi projetado para:

- Respeitar governança Microsoft
- Garantir isolamento total por cooperativa
- Evitar arquitetura paralela
- Permitir evolução controlada
- Manter padrão técnico corporativo

---

SIGA – Plataforma de Governança Operacional  
Baseada em Microsoft Power Platform
