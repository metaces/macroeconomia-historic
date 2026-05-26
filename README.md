# Análise Macro Brasil

Projeto de análise macrofinanceira diária focada no mercado brasileiro, desenvolvido com o Grok (xAI).

## 🎯 Objetivo

Gerar relatórios consistentes e profissionais de análise macro intradiária e de fechamento para os mercados de Dólar Futuro (DOLFUT), Índice Futuro (INDFUT), Ibovespa e ativos correlacionados.

## 📁 Estrutura do Projeto

```bash
analise-macro-brasil/
├── historico/
│   └── historico.json                 # Base histórica de relatórios
├── prompts/
│   ├── prompt-mestre-unico.md         # Prompt principal (mestre + checklist)
│   └── checklist.md                   # Checklist de fatores macro
├── relatorios/                        # Relatórios gerados (um por dia)
│   ├── 2026-05-26-relatorio.md
│   └── ...
├── templates/                         # Templates adicionais (futuro)
├── .gitignore
└── README.md
```

## 🚀 Como Usar

### 1. Gerar Relatório Diário
1. Abra uma conversa com o Grok
2. Cole o conteúdo completo do arquivo `prompts/prompt-mestre-unico.md`
3. Envie a mensagem

### 2. Atualizar Histórico
Após gerar o relatório, copie a parte relevante e adicione ao `historico.json`.

### 3.Comandos

Inicio do dia

Data de hoje: 26/05/2026
Horário atual: 08:30 BRT
Use o arquivo historico/historico.json como referência.

Envie o prompt → Grok vai gerar o relatório intradiário completo.

Fechamento

Data de hoje: 26/05/2026
Horário do corte: 17:30 BRT (fechamento)
Gere o relatório de fechamento consolidado.

### 4. Atualização do Histórico (Importante)
Após gerar o relatório do dia, atualize o historico.json:

Copie o bloco JSON gerado no final do relatório (ou peça ao Grok para gerar só o JSON).
Cole no arquivo historico/historico.json como novo objeto.
Faça commit no GitHub.

### 5. Commit no GitHub
```bash
git add .
git commit -m "relatorio: 2026-05-26"
git push
```

## 📋 Arquivos Principais

- **`prompt-mestre-unico.md`** → Prompt completo (mestre + checklist)
- **`historico.json`** → Histórico de dias anteriores
- **`relatorios/`** → Arquivos markdown dos relatórios diários

## 🛠 Ferramentas e Fontes

- **Fontes oficiais**: BCB, IBGE, FGV, B3, BLS, U.S. Treasury, Bloomberg/Reuters
- **Ferramenta**: Grok (xAI)

## 📈 Próximos Passos (Roadmap)

- [ ] Automatizar atualização do `historico.json`
- [ ] Criar GitHub Actions para gerar relatório diário
- [ ] Dashboard simples (Streamlit ou similar)
- [ ] Backtesting de estratégias baseadas nos relatórios

---

**Projeto mantido com ❤️ usando Grok**

Última atualização: 26/05/2026
