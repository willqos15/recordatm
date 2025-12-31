# Plataforma de Cadastro — Promoção Grupo Mirante

Este projeto consiste em uma **plataforma web de cadastro online**, desenvolvida para atender uma **promoção de emissora Mirante, o canal Record local de Altamira - Pará**, onde participantes concorriam a prêmios através de **cupons com códigos únicos**.

A solução foi pensada para ser **simples, eficiente e de baixo custo**, atendendo às necessidades reais do cliente sem uso de infraestrutura complexa.

---

## Contexto do Projeto

A emissora precisava de uma forma de:

- Permitir o **cadastro online** dos participantes
- Validar **códigos promocionais (cupons)**
- Impedir a **reutilização de códigos**
- Registrar os dados de forma organizada
- Evitar custos com hospedagem de backend e banco de dados

O projeto foi desenvolvido utilizando **HTML, CSS e JavaScript**, integrando-se ao **Google Sheets via Google Apps Script**.

---

## Ideia e Solução Proposta

Em vez de utilizar um banco de dados tradicional, optei por uma solução baseada em **Google Planilhas**, pois:

- O volume de dados era simples e controlado
- Não havia necessidade de consultas complexas
- O cliente queria **evitar custos recorrentes**
- A equipe já tinha familiaridade com Excel / Google Sheets


---

## Funcionamento Geral

1. O participante acessa a página da promoção
2. É incentivado a se inscrever no canal do YouTube da emissora
3. Após a inscrição, o formulário de cadastro é liberado
4. O participante preenche:
   - Nome completo
   - Número de celular
   - Código do cupom
5. O formulário envia os dados para um **Google Apps Script**
6. O script valida o código informado comparando com uma **lista de códigos válidos** em uma planilha
7. Se o código:
   - For válido e ainda não usado → cadastro aprovado
   - Já tiver sido usado → cadastro recusado
   - Não existir → cadastro inválido
8. Quando um código é usado com sucesso, ele é **marcado na planilha**, impedindo reutilização

---

## Controle de Dados

A solução utiliza duas planilhas principais:

- **Planilha de Códigos**
  - Lista de códigos válidos
  - Status de uso (disponível / utilizado)

- **Planilha de Cadastros**
  - Nome do participante
  - Contato
  - Código utilizado
  - Data e hora do cadastro

Todo o controle acontece automaticamente via **Apps Script**, sem necessidade de intervenção manual.

---

## Validações Implementadas

- Nome com tamanho mínimo
- Número de celular com DDD
- Conversão automática do código para letras maiúsculas
- Verificação obrigatória de inscrição no canal
- Bloqueio de envio enquanto houver erros no formulário
- Mensagens claras de retorno ao usuário (sucesso, código inválido, código usado)

---

## Tecnologias Utilizadas

- HTML
- CSS
- JavaScript
- Google Apps Script
- Google Sheets

---

## Considerações Finais

Este projeto demonstra uma abordagem prática de **resolver um problema real com a tecnologia adequada**, sem exagero de complexidade.

A escolha do Google Sheets como “backend” foi intencional, considerando:
- Escopo do projeto
- Orçamento do cliente
- Facilidade de manutenção
- Rapidez de implementação

O resultado foi uma plataforma funcional, acessível e alinhada às necessidades da promoção.
