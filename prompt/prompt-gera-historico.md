Transforme o relatório macrofinanceiro do dia em um objeto JSON seguindo exatamente esta estrutura:

{
  "date": "AAAA-MM-DD",
  "cut_time": "HH:MM BRT",
  "summary": "Resumo executivo do dia em 2-3 frases",
  "impacts": {
    "dolfut": ["principais fatores que impactaram o dólar futuro"],
    "indfut": ["principais fatores que impactaram o índice futuro"]
  },
  "complements": {
    "di_curve": {"short": "valor", "medium": "valor", "long": "valor"},
    "cds_brazil_5y": "valor",
    "ibovespa": "valor",
    "sp500": "valor",
    "nasdaq": "valor",
    "brent": "valor",
    "wti": "valor",
    "vix": "valor"
  },
  "pending": ["lista de indicadores aguardando divulgação"]
}

Regras:
- Use apenas valores oficiais ou marque como "aguardando divulgação".
- Respeite o formato JSON válido.
- Não inclua comentários ou texto fora do objeto JSON.
