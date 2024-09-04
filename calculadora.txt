#!/bin/bash
# Como executar a calculadora
# 1 Primeiro execute torne executável chmod +x calculadora.sh
# 2 Segundo execute o script ./calculadora.sh


# Adição
add() {
    echo "Resultado: $(($1 + $2))"
}

# Subtração
subtract() {
    echo "Resultado: $(($1 - $2))"
}

# Multiplicação
multiply() {
    echo "Resultado: $(($1 * $2))"
}

# Divisão
divide() {
    if [ $2 -eq 0 ]; then
        echo "Erro: divisão por zero" #não sendo possível efetuar uma divisão por 0
    else
        echo "Resultado: $(($1 / $2))"
    fi
}

echo "Por favor escolha uma das operações: +, -, *, /"
read operation
echo "Digite o primeiro número:"
read num1
echo "Digite o segundo número:"
read num2
echo "Digite o terceiro número:"
read num3
echo "Agrademos a preferência, tenha um exelente dia !!!"
case $operation in
    +)
        add $num1 $num2
        ;;
    -)
        subtract $num1 $num2
        ;;
    \*)
        multiply $num1 $num2
        ;;
    /)
        divide $num1 $num2
        ;;
    *)
        echo "Operação inválida"
        ;;
esac
