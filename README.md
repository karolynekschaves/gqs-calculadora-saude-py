# 🚫 Calculadora saúde (ajustando erros)

# 💡O que se trata 
Vamos analisar um código python proposto no arquivo /calculadora_saude.py e analisar o que não esta correto, correções estarão disponíveis no arquivo /calculadora_saude_ajustado.py

⚠️ Ao baixar esses arquivos recomendasse que tenha o Visual Studio baixando e a extensão python confiável para executar o arquivo corretamente ⚠️

## 📝 Analisando erros

## #1 Erro# 🚨

Entrada de dados : Quando damos entrada para escolhermos a opçao solicitada no painel só retorna opção invalida

<img width="138" height="171" alt="image" src="https://github.com/user-attachments/assets/f6af280a-83ff-4938-8361-342683ef5107" />

## Onde esta o erro
```
 Linha 39 opcao = input("Escolha uma opção (1-4): ")
 Linha 40 return opcao 
```
 No momento que é digitada opção ela é tratada como string devido ao input, por isso vamos ajustar esse input=texto para números inteiros INT
 
## Ajuste ✅
```
 Linha 39 opcao = int(input("Escolha uma opção (1-4): "))
 Linha 40 return opcao 
```

## #2 Erro# 🚨

Formula errada para calcular IMC : Para o calculo do IMC é usado a seguinte formula 
peso/(altura²) já no nosso código esta multiplicando em vez de fazer potenciação resultando em cálculos errados 

## Onde esta o erro
```
Linha 5 imc = peso / (altura * 2)
Linha 6 return imc
```
## Ajuste ✅
```
Linha 5 imc = peso / (altura * altura)
Linha 6 return imc
```
## #3 Erro# 🚨

Calculo de quantos litros de agua por dia: Quando entramos na segunda opção, para sabermos litros por peso, o código esta dividindo ao invés de multiplicar peso por 35 milímetros

## Onde esta o erro
```
linha 21 litros = (peso / 35)
linha 22 return litros
```
## Ajuste ✅
```
linha 21 litros = (peso * 35/1000)  # Convertendo ml para litros)
linha 22 return litros
```
## #4 Erro# 🚨

Calcular frequência cardíaca máxima: Quando entramos nessa opção, o código esta usando a formula de soma ( 220 + idade) o que é incorreto, a forma certa é a subtração

## Onde esta o erro
```
linha 24 fc_max = 220 + idade
linha 25 return fc_max
```
## Ajuste ✅
```
linha 24 fc_max = 220 - idade
linha 25 return fc_max
```
## #5 Erro# 🚨

Finalização infinita : ao escolhermos a opção 4 para sairmos ele apenas continua voltando para escolha de opções novamente, para ressorvermos isso vamos aplicar o break a baixo da linha para quebrar o loop e encerrar corretamente 

## Onde esta o erro
```
linha 60 print("Encerrando o sistema...")
linha 61 print("Obrigado por usar nosso sistema!")
```
## Ajuste ✅
```
linha 60 print("Encerrando o sistema...")
linha 61 print("Obrigado por usar nosso sistema!")
break  # Adicionando break para sair do loop
```
