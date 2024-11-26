-- Funções matemáticas avançadas
function soma(a, b)
    return a + b
end

function subtrair(a, b)
    return a - b
end

function multiplicar(a, b)
    return a * b
end

function dividir(a, b)
    if b ~= 0 then
        return a / b
    else
        return "Divisão por zero não é permitida"
    end
end

print(soma(10, 15))  -- Saída: 25
print(subtrair(20, 5))  -- Saída: 15
print(multiplicar(6, 7))  -- Saída: 42
print(dividir(40, 8))  -- Saída: 5

-- Função que encontra o maior número em uma tabela
function encontrarMaior(t)
    local maior = t[1]
    for i = 2, #t do
        if t[i] > maior then
            maior = t[i]
        end
    end
    return maior
end

local numeros = {10, 20, 30, 25, 15}
print("Maior número:", encontrarMaior(numeros))  -- Saída: 30

-- Tabela de frutas com funcionalidades adicionais
local frutas = {"Maçã", "Banana", "Laranja", "Morango", "Uva"}

-- Função para listar frutas
function listarFrutas(frutas)
    for i, fruta em ipairs(frutas) do
        print("Fruta " .. i .. ": " .. fruta)
    end
end

listarFrutas(frutas)

-- Função para adicionar uma fruta à tabela
function adicionarFruta(frutas, fruta)
    table.insert(frutas, fruta)
    print(fruta .. " adicionada à lista.")
end

adicionarFruta(frutas, "Manga")
listarFrutas(frutas)

-- Função para remover uma fruta da tabela
function removerFruta(frutas, fruta)
    for i, v em ipairs(frutas) do
        if v == fruta then
            table.remove(frutas, i)
            print(fruta .. " removida da lista.")
            break
        end
    end
end

removerFruta(frutas, "Banana")
listarFrutas(frutas)

-- Função para buscar uma fruta na tabela
function buscarFruta(frutas, fruta)
    for i, v em ipairs(frutas) do
        if v == fruta then
            return true
        end
    end
    return false
end

print("A tabela contém 'Laranja'? ", buscarFruta(frutas, "Laranja"))  -- Saída: true
print("A tabela contém 'Banana'? ", buscarFruta(frutas, "Banana"))  -- Saída: false

-- Função para calcular a média de uma tabela de números
function calcularMedia(t)
    local soma = 0
    for i = 1, #t do
        soma = soma + t[i]
    end
    return soma / #t
end

print("Média dos números:", calcularMedia(numeros))  -- Saída: 20
