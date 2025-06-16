# Relatório de Análise Exploratória de Dados (EDA) - Fatores de Evasão de Clientes

## 📌 Introdução

Este relatório apresenta os principais insights da análise exploratória de dados realizada sobre o comportamento de evasão (churn) de clientes da **TelecomX**.  
O objetivo foi identificar padrões e fatores que podem influenciar a decisão dos clientes de cancelar seus serviços, utilizando métricas descritivas e visualizações.

---

## 1. Panorama Geral da Evasão (Churn)

Antes de mergulharmos nas variáveis específicas, é crucial entender a dimensão do problema de evasão:

- **Total de Clientes Analisados**: 7.256  
- **Clientes que Não Tiveram Evasão (Não Churn)**: 5.387 (~74,24%)  
- **Clientes que Tiveram Evasão (Churn)**: 1.869 (~25,76%)  

> **Insight:** Quase um quarto dos clientes da TelecomX está cancelando os serviços, o que representa uma taxa de churn significativa e requer atenção.

---

## 2. Análise da Evasão por Variáveis Categóricas

### 2.1. Gênero

- Feminino: 26,18%
- Masculino: 25,35%

> **Insight:** O gênero, por si só, não parece ser um fator significativo na propensão à evasão.

---

### 2.2. Idoso (`SeniorCitizen`)

- Não idosos: 22,93%  
- Idosos: 40,27%

> **Insight:** Idosos apresentam uma taxa de evasão quase duas vezes maior. Segmento crítico.

---

### 2.3. Parceiro (`Partner`)

- Sem parceiro: 32,03%  
- Com parceiro: 19,07%

> **Insight:** A presença de um parceiro pode indicar maior estabilidade e menor evasão.

---

### 2.4. Dependentes (`Dependents`)

- Sem dependentes: 30,34%  
- Com dependentes: 15,02%

> **Insight:** Ter dependentes reduz significativamente a evasão.

---

### 2.5. Serviço de Telefone (`PhoneService`)

- Com telefone: 25,93%  
- Sem telefone: 24,11%

> **Insight:** Diferença pouco relevante. Não é fator decisivo.

---

### 2.6. Múltiplas Linhas (`MultipleLines`)

- Sem múltiplas linhas: 24,29%  
- Com múltiplas linhas: 27,77%

> **Insight:** Pequeno aumento no churn com múltiplas linhas.

---

### 2.7. Serviço de Internet (`InternetService`)

- DSL: 18,49%  
- Fibra Óptica: 40,56%  
- Sem serviço: 7,17%

> **Insight:** Fibra Óptica tem a maior taxa de churn — merece investigação.

---

### 2.8. Segurança Online (`OnlineSecurity`)

- Sem segurança: 30,37%  
- Com segurança: 14,22%

> **Insight:** Segurança online está associada à maior retenção.

---

### 2.9. Backup Online (`OnlineBackup`)

- Sem backup: 28,30%  
- Com backup: 20,92%

> **Insight:** Backup online também ajuda a reduzir churn.

---

### 2.10. Proteção de Dispositivo (`DeviceProtection`)

- Sem proteção: 27,76%  
- Com proteção: 21,91%

> **Insight:** Proteção de dispositivo contribui para maior fidelidade.

---

### 2.11. Suporte Técnico (`TechSupport`)

- Sem suporte: 30,24%  
- Com suporte: 14,76%

> **Insight:** Um dos fatores com maior impacto na retenção.

---

### 2.12. Streaming TV (`StreamingTV`)

- Sem TV: 23,60%  
- Com TV: 29,22%

> **Insight:** Pode indicar que o serviço não atende às expectativas.

---

### 2.13. Streaming Filmes (`StreamingMovies`)

- Sem filmes: 23,67%  
- Com filmes: 29,06%

> **Insight:** Similar à TV, pode indicar baixo valor percebido.

---

### 2.14. Contrato (`Contract`)

- Dois anos: 2,77%  
- Um ano: 10,94%  
- Mensal: 41,32%

> **Insight:** Contratos mensais têm a maior taxa de evasão. Incentivar contratos mais longos.

---

### 2.15. Fatura Digital (`PaperlessBilling`)

- Sem fatura digital: 15,91%  
- Com fatura digital: 32,50%

> **Insight:** Pode indicar maior propensão à troca por parte de clientes mais digitais.

---

### 2.16. Método de Pagamento (`PaymentMethod`)

- Cartão de crédito (automático): 14,81%  
- Transferência bancária (automática): 16,26%  
- Cheque enviado: 18,59%  
- Cheque eletrônico: 43,80%

> **Insight:** Cheque eletrônico está fortemente associado à evasão. Automatização é preferível.

---

## 3. Resumo dos Principais Fatores de Risco para Evasão (Churn)

### Perfis com **alta taxa de churn**:

- 👴 **Idosos**: +40%
- 💔 **Sem parceiro/dependentes**  
- 🌐 **Com Fibra Óptica**  
- ❌ **Sem serviços adicionais de valor** (Segurança, Backup, Suporte, Proteção)
- 📆 **Contrato mensal**: ~41%
- 📩 **Fatura digital**
- 💸 **Pagamento via cheque eletrônico**
- 📺 **Com serviços de streaming**

---

### Perfis com **baixa taxa de churn** (fatores de proteção):

- ✅ Ter parceiro e/ou dependentes  
- ⏳ Contrato de 1 ou 2 anos  
- 🛡️ Usar serviços adicionais  
- 💳 Pagamentos automáticos  
- 📉 Sem internet ou com DSL

---

## 4. Próximos Passos e Recomendações

Com base nesses insights, a TelecomX deveria considerar:

- **Focar em Clientes de Contrato Mensal**: Oferecer incentivos para migrar para contratos de um ou dois anos.  
- **Melhorar a Experiência da Fibra Óptica**: Investigar por que clientes de Fibra Óptica estão evadindo tanto. Pode ser qualidade de serviço, velocidade ou problemas de atendimento.  
- **Promover Serviços Adicionais**: Destacar os benefícios da Segurança Online, Backup, Proteção de Dispositivo e Suporte Técnico, pois eles claramente aumentam a retenção.  
- **Reavaliar o Método de Pagamento "Cheque eletrônico"**: Entender as razões da alta evasão associada a ele.  
- **Segmentar Campanhas de Retenção**: Criar campanhas direcionadas para os grupos de alto risco (Idosos, clientes sem parceiro/dependentes, etc.).  
- **Investigar a Fatura Digital e os Serviços de Streaming**: Entender por que esses "facilitadores" ou "extras" estão associados a maior churn.
