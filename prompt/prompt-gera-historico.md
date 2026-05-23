Instrução principal:
Transforme o relatório macrofinanceiro do dia em um objeto JSON seguindo exatamente esta estrutura:

{
  "date": "AAAA-MM-DD",
  "cut_time": "HH:MM BRT",
  "summary": "Resumo executivo do dia em 2-3 frases",
  "impacts": {
    "dolfut": ["..."],
    "indfut": ["..."]
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
  "pending": ["lista de indicadores aguardando divulgação"],
  "validation_summary": "Resumo da validação (1–2 frases)"
}

Regras estritas de leitura, formatação e fontes:

Fonte dos dados: Basear o relatório exclusivamente em dados consolidados de fechamento do mercado para a data de corte; usar apenas valores oficiais de fechamento; quando um dado oficial de fechamento não estiver disponível, marcar explicitamente "aguardando divulgação".

Leitura do histórico:

Ler historico.json.

Usar somente objetos cujas chaves date existam no arquivo.

Filtrar eventos com date entre (data_corte - 60 dias) e data_corte inclusive.

Incorporar impactos acumulados dos eventos passados (juros, inflação, risco global, fluxo estrangeiro, CDS, setorial, cross-asset) apenas a partir dos objetos filtrados.

Prioridade de valores:

Se houver divergência entre historico.json e um valor oficial de fechamento confirmado, usar o valor oficial.

Quando o valor oficial não estiver disponível, preencher o campo com "aguardando divulgação" e listar o indicador em pending.

Formato e unidades:

Todos os campos numéricos devem ser strings com unidades explícitas: DI em % (ex.: "14.40%"), CDS em bps (ex.: "117.8 bps"), petróleo em USD/bbl (ex.: "107.5 USD/bbl"), índices com variação entre parênteses (ex.: "181908 (-1.19%)"), VIX em número com unidade % quando aplicável (ex.: "18.3" ou "18.3%" conforme fonte).

cut_time deve ser string no formato "HH:MM BRT".

Pending:

Padronizar entradas pendentes como "Nome do indicador — aguardando divulgação".

Exemplos típicos: "IGP-10 (FGV) — aguardando divulgação", "Fluxo estrangeiro diário B3 — aguardando divulgação", "Leilões e operações do Banco Central — aguardando divulgação".

Consistência:

Garantir que valores em complements sejam consistentes com os eventos e impactos descritos.

Se um complemento for "aguardando divulgação", esse indicador deve aparecer em pending.

Saída:

O JSON final deve ser válido (sem comentários, sem texto fora do objeto).

summary em português com 2–3 frases refletindo o fechamento consolidado e as correlações principais.

impacts deve listar os principais fatores que influenciaram DOLFUT e INDFUT no fechamento.

Incluir validation_summary com 1–2 frases confirmando que o prompt mestre executou a validação e o resultado (OK ou lista resumida de pendências).

Observação final:

Não inventar valores; quando houver incerteza ou ausência de fechamento oficial, usar "aguardando divulgação".