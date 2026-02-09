# 🔎 Relatório de Segurança Cibernética – Investigação de Phishing

**Data da análise:** 24/11/2024  
**Categoria:** Phishing / Engenharia Social  
**Finalidade:** Uso educacional e conscientização em Segurança da Informação  

---

## 📌 Descrição do Caso

Em **24 de novembro de 2024**, foi identificado um e-mail suspeito informando a existência de uma **multa de trânsito pendente** no valor de **R$ 195,00**, solicitando acesso imediato a um link para pagamento.

A verificação realizada diretamente no **site oficial do DETRAN** confirmou que **não havia qualquer multa registrada**, indicando uma possível **tentativa de phishing**.

Para a investigação técnica, foram utilizadas as seguintes ferramentas:

- Nikto  
- Curl  
- Whois  

---

## 🧪 Análise Técnica

### 1. Resultados do Scan com Nikto

- **Domínio analisado:** `canaacolorado.com.br`  
- **Endereço IP:** `131.72.52.10`

**Problemas de segurança identificados:**

- Ausência do cabeçalho **X-Frame-Options**  
  - Possível exploração por **ataques de clickjacking**.
- Ausência do cabeçalho **Strict-Transport-Security (HSTS)**  
  - Permite cenários de downgrade para conexões HTTP inseguras.
- **Cabeçalho Content-Type não definido corretamente**  
  - Pode causar interpretação incorreta do conteúdo pelo navegador.
- **Comportamento de redirecionamento suspeito**  
  - Página principal redireciona para `/avaliacaofiscal.site1`.

➡️ Indica **infraestrutura potencialmente maliciosa ou mal configurada**.

---

### 2. Resultados da Consulta Whois

- **Domínio:** `canaacolorado.com.br`  
- **Registrante:** Pessoa física (não governamental)  
- **Provedor DNS:** `todasolucao.com.br`  
- **Data de criação:** 30/11/2023  
- **Data de expiração:** 11/11/2025  

**Observação:**  
O domínio é **recente** e **não possui qualquer associação com órgãos governamentais brasileiros ou serviços do DETRAN**.

---

## 🖥️ Características da Página Fraudulenta

A página identificada apresenta:

- Título: **“Aviso de Regularização Pendente”**
- Suposta infração:
  - *Não utilização do cinto de segurança*
- Valores exibidos:
  - **R$ 195,23** (valor original)  
  - **R$ 117,14** (valor com desconto)
- Botão de ação destacado:
  - **“Acessar Gov.br”**

Apesar de simular comunicação oficial, a verificação do domínio confirma **ausência de legitimidade**, caracterizando **tentativa de engenharia social**.

---

## 🚨 Conclusão

### ✔️ Indícios confirmados de phishing

A investigação demonstra que o domínio **canaacolorado.com.br** foi utilizado como parte de uma **campanha de phishing**, com o objetivo de **se passar por notificação oficial de autoridade de trânsito**.

### 🔍 Evidências técnicas

- Ausência de **cabeçalhos HTTP essenciais de segurança**.  
- **Registro recente do domínio** sem vínculo governamental.  
- Uso de **engenharia social baseada em urgência** para induzir pagamento imediato.

---

## 🛡️ Recomendações de Segurança

- Nunca acessar links de pagamento recebidos por **e-mail ou SMS não solicitados**.  
- Verificar multas ou débitos **exclusivamente em portais oficiais do DETRAN**.  
- Reportar domínios suspeitos para:
  - **CERT.br**
  - Provedor de hospedagem
  - Autoridades competentes

---

## 📄 Licença e Aviso Legal

Este relatório é disponibilizado **exclusivamente para fins educacionais, de pesquisa e conscientização em segurança cibernética**.  
Nenhum dado pessoal sensível é intencionalmente divulgado.

---
