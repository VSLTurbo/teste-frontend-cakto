# Teste Prático - Front-End Sênior (Cakto)

**Título:** Mini Checkout de Produto Digital

---

## Objetivo

Avaliar a capacidade do(a) candidato(a) de implementar uma interface de checkout realista e estratégica para um produto digital na plataforma Cakto. Este teste foi desenhado com base no modelo de negócio da empresa, simulando desafios reais que a equipe enfrenta no dia a dia.

**Duração sugerida:** 45 minutos

---

## Cenário

Você precisa construir um mini-checkout para venda de um curso digital na plataforma. O componente precisa calcular taxas, mostrar um resumo em tempo real e destacar opções de maior conversão (como o PIX com taxa zero).

### Produto Mock

```json
{
  "id": 1,
  "name": "Curso de Marketing Digital 2025",
  "originalPrice": 497.00,
  "currentPrice": 297.00,
  "producer": "João Silva",
  "format": "digital",
  "deliveryTime": "imediato"
}
```

---

## Funcionalidades Obrigatórias

### 1. Calculadora de Taxas Inteligente

- **PIX:** 0% de taxa
- **Cartão à vista:** 3.99%
- **Cartão parcelado:** 4.99% + 2% por parcela extra
- Mostrar valor líquido que o produtor recebe

### 2. Formulário de Checkout

- Email (obrigatório)
- CPF com máscara e validação básica
- Método de pagamento (PIX ou Cartão)
- Se for Cartão: seleção de parcelas (1x até 12x)

### 3. Resumo Dinâmico

- Atualizar em tempo real com cada mudança no formulário
- Mostrar economia ao escolher PIX
- Exibir:
  - Valor bruto
  - Taxa da plataforma
  - Valor líquido para o produtor

### 4. Experiência de Usuário Otimizada

- Mobile-first obrigatório
- Destaque visual para o PIX
- Validação em tempo real (sem bloquear digitação)
- Loading state no botão "Finalizar Compra"

---

## Desafios Técnicos

### 1. Cálculo de Parcelas e Taxas

```typescript
function calcularParcelas(valor: number, maxParcelas: number): Parcela[] {
  // PIX: sem taxa
  // 1x cartão: valor + 3.99%
  // 2x cartão: (valor + 4.99%) / 2 + 2%
  // 3x cartão: (valor + 4.99%) / 3 + 4%
  // ...
}
```

### 2. Validação de CPF

- Aceitar formatos: `123.456.789-01` ou `12345678901`
- Validar dígitos verificadores

### 3. Otimização de Estado e Performance

- Usar React state eficientemente (evitar re-renders desnecessários)
- Implementar Server Components para dados estáticos
- Usar Client Components apenas para interatividade
- Atualizar dados do resumo em tempo real
- Implementar lazy loading e otimizações de bundle

### 4. Decisões Arquiteturais (Valorizado)

- Estrutura de componentes reutilizáveis
- Gerenciamento de estado eficiente
- Tratamento de erros e edge cases
- Performance e otimizações

---

## Layout Esperado (Mobile-First)

```
[ PRODUTO ]
Curso de Marketing Digital 2025
De R$ 497,00 por R$ 297,00

[ DADOS PESSOAIS ]
Email: [____________]
CPF:   [___...___]

[ PAGAMENTO ]
○ PIX (Taxa 0% 🔥)
○ Cartão
   └ Parcelas: [1x ▼]

[ RESUMO DO PEDIDO ]
Produto:      R$ 297,00
Taxa Cakto:   R$ 0,00
Total:        R$ 297,00
-------------------------
João recebe:  R$ 297,00

[ FINALIZAR COMPRA ] 🚀
```

---

## Stack Obrigatória

- **React + TypeScript**
- **TailwindCSS**
- **Next.js** (opcional, mas valorizado)
- **Testes básicos** (opcional, mas valorizado)

---

## Critérios de Avaliação

| Critério | Peso | Avaliação |
|----------|------|-----------|
| **Decisões Técnicas** | 40% | Arquitetura, organização, padrões, escalabilidade |
| **Business Logic** | 30% | Cálculo de taxas, validações, lógica de negócio |
| **UX / Conversão** | 30% | Mobile-first, experiência do usuário, performance |

---

## Níveis de Entrega

| Nível | O que esperamos ver |
|-------|---------------------|
| **Pleno** | Layout funcional, cálculos básicos corretos, responsivo simples |
| **Sênior** | Arquitetura limpa, componentes reutilizáveis, tratamento de edge cases, performance otimizada |
| **Excepcional** | Decisões técnicas excepcionais, micro-interações, A11Y, testes, documentação clara |

---

## Entrega Esperada

### Opção 1: Repositório GitHub (Recomendado)
- Crie um repositório público no GitHub
- Implemente o projeto seguindo as especificações
- Adicione um README.md com:
  - Decisões técnicas (2-3 parágrafos)
  - Como rodar localmente
  - Comandos para executar testes (se aplicável)
- Envie o link do repositório

### Opção 2: Arquivo ZIP
- Implemente o projeto localmente
- Crie um README.md com as informações acima
- Compacte todos os arquivos em um ZIP
- Envie o arquivo ZIP

### Resposta Bônus (Obrigatória)
Responda à pergunta:

> **"Se tivesse mais tempo, o que você faria para aumentar a conversão deste checkout?"**

### Estrutura do README.md (Obrigatória)

Seu README deve conter:

```markdown
# Teste Front-End Cakto - [Seu Nome]

## Decisões Técnicas

[2-3 parágrafos explicando suas principais decisões arquiteturais,
escolhas de tecnologia e por que você fez essas escolhas]

## Como Executar

```bash
npm install
npm run dev
```

## Testes (se aplicável)

```bash
npm test
```

## Resposta Bônus

[Suas ideias para aumentar a conversão do checkout]
```

### Como Criar o Repositório

1. **Crie um repositório no GitHub:**
   - Acesse [github.com](https://github.com)
   - Clique em "New repository"
   - Nome: `teste-frontend-cakto-[seu-nome]`
   - Público
   - Não inicialize com README

2. **Clone e configure localmente:**
   ```bash
   git clone https://github.com/seu-usuario/teste-frontend-cakto-[seu-nome].git
   cd teste-frontend-cakto-[seu-nome]
   ```

3. **Implemente o projeto e faça commit:**
   ```bash
   git add .
   git commit -m "Implementação do teste front-end Cakto"
   git push origin main
   ```

---

## Contato

Para dúvidas sobre o teste, entre em contato com a equipe de recrutamento da Cakto.

**Boa sorte!** 🚀
