# faturamento_distribuidora

def calcular_estatisticas_faturamento(faturamento_diario):
    if not faturamento_diario:
        return None

    menor_valor = min(faturamento_diario)
    maior_valor = max(faturamento_diario)

    media_mensal = sum(faturamento_diario) / len(faturamento_diario)

    dias_acima_da_media = sum(1 for valor in faturamento_diario if valor > media_mensal)

    return menor_valor, maior_valor, dias_acima_da_media

# Exemplo de uso
faturamento_diario = [1000, 1200, 800, 1500, 1300, 1100, 1600, 900, 950, 1200]

resultados = calcular_estatisticas_faturamento(faturamento_diario)

if resultados:
    menor_valor, maior_valor, dias_acima_da_media = resultados
    print(f"Menor valor de faturamento: {menor_valor}")
    print(f"Maior valor de faturamento: {maior_valor}")
    print(f"Número de dias acima da média mensal: {dias_acima_da_media}")
else:
    print("Vetor de faturamento diário vazio.")
