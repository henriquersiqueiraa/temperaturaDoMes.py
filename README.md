def temperaturaDoMes(temperaturas):
    print("A menor temperatura do mês foi: ", min(temperaturas), "ºC")
    print("A maior temperatura do mês foi: ", max(temperaturas), "ºC")

def maxima(temps):
    max_temp = temps[0]
    i = 1
    while i < len(temps):
        if temps[i] > max_temp:
            max_temp = temps[i]
        i = i + 1
    return max_temp

def minima(temps):
    min_temp = temps[0]
    i = 1
    while i < len(temps):
        if temps[i] < min_temp:
            min_temp = temps[i]
        i = i + 1
    return min_temp

def teste_pontual(func, temp, valor_esperado):
    resultado = func(temp)
    if valor_esperado != resultado:
        print("Valor errado para array ", temp)
        print("Valor esperado: ", valor_esperado, ". Valor retornado: ", resultado)
    else:
        print("Teste passou para array ", temp)

def teste_minima():
    print("Iniciando os testes de mínima")
    teste_pontual(minima, [0], 0)
    teste_pontual(minima, [0, 0, 0, 0, 0, 0], 0)
    teste_pontual(minima, [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 0)
    teste_pontual(minima, [36, 37, 29, 39, 34, 32, 33, 30, 24, 26, 28], 24)
    teste_pontual(minima, [-14, -15, -8, 0, 9, 13, 15], -15)
    print("Finalizando os testes de mínima")

def teste_maxima():
    print("Iniciando os testes de máxima")
    teste_pontual(maxima, [0], 0)
    teste_pontual(maxima, [0, 0, 0, 0, 0, 0], 0)
    teste_pontual(maxima, [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 10)
    teste_pontual(maxima, [36, 37, 29, 39, 34, 32, 33, 30, 24, 26, 28], 39)
    teste_pontual(maxima, [-14, -15, -8, 0, 9, 13, 15], 15)
    print("Finalizando os testes de máxima")

# Chamando os testes
teste_minima()
teste_maxima()
