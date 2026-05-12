Instrução:
Gerar relatório macrofinanceiro intradiário para o mercado brasileiro com corte às 09:00 BRT na data [DD/MM/YYYY]. 
Seguir estritamente as regras abaixo:

1. Histórico acumulado:
- Antes de gerar o relatório do dia, considerar o arquivo historico.json, que contém um array de objetos com os relatórios anteriores.
- Ler todos os objetos até a data limite informada pelo usuário.
- Utilizar apenas os eventos dentro de uma janela de 60 dias anteriores à data limite.
- Incorporar os impactos acumulados (juros, inflação, risco global, fluxo estrangeiro, CDS, setorial, cross-asset) na análise do dia.
- Evidenciar como os eventos passados influenciam o cenário atual.

2. Fontes obrigatórias:
Primeiro nível: consultar calendários oficiais: Banco Central do Brasil, IBGE, FGV, Tesouro Nacional, BLS, BEA, Federal Reserve, U.S. Treasury.
Segundo nível: confirmar cada dado relevante em Bloomberg ou Reuters.
Regra: sempre usar valores oficiais; se não houver divulgação, indicar “aguardando divulgação”.

3. Filtros de análise:
Retornar cinco itens mais relevantes por filtro:
- Filtro 0 – Eventos da madrugada
- Filtro 1 – Juros (Selic, DI futuro, Treasuries EUA)
- Filtro 2 – Inflação (IPCA, CPI EUA)
- Filtro 3 – Crescimento econômico (PIB Brasil/EUA, atividade)
- Filtro 4 – Risco global (VIX, geopolítica, commodities)
- Filtro 5 – Política monetária (BCB/Fed)
- Filtro 6 – Fluxo de capital (balança comercial, fluxo estrangeiro na B3)
- Filtro adicional – Clima global (peso 50%) e Resposta local (peso 20%)
- Filtro Caminho de menor resistência
- Filtro Justificativa para risco ou proteção
- Filtro Ritmo intradiário / Motivadores do dia

4. Complementos obrigatórios:
- Movimentos da curva de juros DI futuro (curto, médio, longo).
- CDS Brasil 5y.
- Fluxo estrangeiro na B3 e análise setorial (commodities, bancos, consumo, energia, industrial).
- Comparação com S&P 500, Nasdaq, Treasuries (10 anos), petróleo (WTI/Brent).
- Índices de volatilidade (VIX) e sentimento global.
- Liquidez e volume inicial (mercado abre travado ou com direção clara).
- Sempre marcar “aguardando divulgação” quando aplicável.

5. Resultado final exigido:
- Cabeçalho: data/hora do corte, hora de geração, fontes consultadas.
- Resumo executivo: síntese dos filtros e correlação observada.
- Tabela de Probabilidades: Dólar Futuro (DOLFUT): Alta vs Baixa (%). Índice Futuro Brasil (INDFUT): Risco vs Proteção (%).
- Seções por filtro: cinco itens mais relevantes, com valor, horário, fonte oficial e confirmação de mercado.
- Complementos técnicos: curva DI, CDS, fluxo estrangeiro, setorial, cross‑asset snapshot.
- Notas: listar indicadores “aguardando divulgação” e divergências entre fontes oficiais e de mercado.
