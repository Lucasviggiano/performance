## 👨‍💻 Autor

**Lucas Viggiano**  
QA Engineer | Software Quality Engineer | Test Automation Engineer

- 🔗 LinkedIn: https://br.linkedin.com/in/lucasviggiano
- 💻 GitHub: https://github.com/LucasViggiano

---

## 📌 Objetivo do Projeto

Este repositório tem como objetivo demonstrar a implementação de testes de performance automatizados utilizando **k6**, avaliando a capacidade do sistema em responder adequadamente sob diferentes níveis de carga.

Os testes permitem medir:

- Tempo de resposta das páginas e APIs
- Percentis de latência (p95)
- Taxa de falhas
- Throughput
- Comportamento com múltiplos usuários simultâneos

---

## 🌐 Sistema Testado

**EBAC Shop**

- Produção: http://lojaebac.ebaconline.art.br
- Local (Docker): http://localhost

---

## 🛠️ Tecnologias Utilizadas

- k6
- JavaScript (ES6)
- Git
- GitHub
- GitHub Actions
- GitHub Pages

---

## 📁 Estrutura do Projeto

```text
performance/
├── scripts/
│   ├── login-performance.js
│   ├── catalog-performance.js
│   ├── checkout-performance.js
│   └── api-performance.js
│
├── results/
│   ├── summary.html
│   ├── summary.json
│   └── metrics.csv
│
├── .github/
│   └── workflows/
│       └── performance.yml
│
├── package.json
├── README.md
└── LICENSE
📈 Estratégia de Testes de Performance

Os testes foram desenvolvidos para validar fluxos críticos da aplicação, incluindo:

Login de usuários
Navegação no catálogo de produtos
Processo de checkout
Consumo da API GraphQL
Thresholds de Qualidade
thresholds: {
  http_req_duration: ['p(95)<3000'],
  http_req_failed: ['rate<0.05']
}

Critérios adotados:

95% das requisições devem responder em menos de 3 segundos
Menos de 5% de falhas permitidas
👥 Cenário de Carga
export const options = {
  vus: 10,
  duration: '30s',
  gracefulStop: '30s'
};
10 usuários virtuais simultâneos
Duração de 30 segundos
Encerramento gradual
▶️ Como Executar
Instalar Dependências
npm install
Executar Teste de Login
k6 run scripts/login-performance.js
Executar Teste de Catálogo
k6 run scripts/catalog-performance.js
Executar Todos os Testes
npm run test:performance
📊 Exemplo de Resultado
✓ http_req_failed........: 0.00%
✓ http_req_duration......: p(95)=2.14s
✓ iterations.............: 150
✓ vus....................: 10
🔄 Integração Contínua (CI/CD)

O projeto pode ser executado automaticamente por meio do GitHub Actions, com geração de artefatos e publicação de relatórios em GitHub Pages.

🌍 GitHub Pages

Relatórios HTML podem ser publicados automaticamente após a execução do pipeline.

Exemplo:

https://lucasviggiano.github.io/performance/

🎓 Contexto Acadêmico

Este projeto integra o Trabalho de Conclusão de Curso (TCC):

Planejamento Estratégico de Testes e Automação da Engenharia de Qualidade na Validação de Fluxos Críticos em Sistemas de Comércio Eletrônico

⭐ Destaques Técnicos
Testes de carga com k6
Thresholds automatizados
Relatórios HTML e JSON
Integração com GitHub Actions
Publicação em GitHub Pages
Estrutura modular e reutilizável
