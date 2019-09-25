# OTES12
Repositório da disciplina 'Tópicos Avançados de Engenharia de Software'

# Objetivo do serviço:
Fornecer serviços de análise de dados como ordenação e limpeza de dados, agrupamento de informações, levantamento numérico de registros e estatística descritiva e indutiva.

#Funções:

##Entrada
###Receber JSON:
Receber arquivo JSON contendo lista infinita de números e salva o mesmo no banco para utilizar durante as requisições de métodos

##Saída
###Ordenação de dados:
Receber objeto e parâmetro de ordenação; Ordenar por categoria informada pelo usuário; Retornar arquivo JSON ordenado

###Limpeza de dados: 
Receber objeto; Remover redundâncias como dados duplicados ou nulos; Retornar arquivo JSON limpo

###Filtro de informações: 
Receber objeto e campo de agrupamento; A partir do campo informado, agrupar dados do arquivo e ordená-los por ordem alfabética; Retornar arquivo JSON apenas com dados filtrados

###Média de valor: 
Receber objeto e campo de cálculo da média; A partir do campo informado, realizar cálculo da média do valor; Retornar valor da média

###Mediana de valor: 
Receber objeto e campo de cálculo da mediana; A partir do campo informado, realizar cálculo da mediana do valor; Retornar valor da mediana

###Desvio Padrão de valor: 
Receber objeto e campo de cálculo do desvio padrão; A partir do campo informado, realizar cálculo do desvio padrão do valor; Retornar valor do desvio padrão

###Previsão de valor (Regressão Linear): 
Receber objeto e campo para previsão; A partir do campo informado, realizar previsão do próximo valor provável através do uso de estatística indutiva; Retornar valor previsto

 
##POST add/numberlist
numberList: [...]  => ex.: [3, 1, 2, ...]
retorno { id: x, status: {code: x, message: "y"} }

##GET order/{id}
ex.: lista de ID = 1: numberList[1]: [3, 1, 2, ...]
retorno { id: x, orderedArray: [1, 2, 3, ...], status: {code: x, message: "y"} }

##GET clean/{id}
ex.: lista de ID = 1: numberList[1]: [3, 1, 1, ...]
retorno { id: x, cleanedArray: [3, 1, ...], status: {code: x, message: "y"} }

##GET filter/{id}
ex.: lista de ID = 1: numberList[1]: [3, 1, 1, ...]
retorno { id: x, filteredArray: [1, 1, ...], status: {code: x, message: "y"} }

##GET average/{id}
ex.: lista de ID = 1: numberList[1]: [1, 3, 2, ...]
retorno { id: x, average: 2, status: {code: x, message: "y"} }

##GET median/{id}
ex.: lista de ID = 1: numberList[1]: [1, 3, 2, ...]
retorno { id: x, median: 3, status: {code: x, message: "y"} }

##GET stdDeviation/{id}
ex.: lista de ID = 1: numberList[1]: [1, 3, 2, ...]
retorno { id: x, stdDeviation: 1, status: {code: x, message: "y"} }
 
##GET futureValue/{id}
ex.: lista de ID = 1: numberList[1]: [1, 2, 3, ...]
retorno { id: x, futureValue: 4, status: {code: x, message: "y"} }

##GET info/{id}
ex.: id: 1
retorno { id: x, numberList: [3, 1, 1, ...], status: {code: x, message: "y"} }

##UPDATE uptList/
{id: x, numberList: [...]}  => ex.: {1, [3, 1, 2, ...]}
retorno {status: {code: x, message: "y"}}

##DELETE delList/{id}
ex.: id: 1
retorno {status: {code: x, message: "y"}}
