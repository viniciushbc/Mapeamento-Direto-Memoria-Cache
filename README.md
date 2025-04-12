# Memória Cache em Python

Este projeto simula o funcionamento básico de uma **memória cache** com mapeamento direto, permitindo observar o comportamento de **cache hit** e **cache miss** em operações de leitura/escrita na memória RAM.

---

## 🚀 Funcionalidades

- Simulação de uma RAM com valores aleatórios.
- Mapeamento direto de endereços de memória para linhas da cache.
- Atualização de valores tanto na RAM quanto na Cache.
- Relatórios visuais (no terminal) da RAM e Cache atualizadas.
- Lógica completa para diferenciar entre:
  - 🟩 **Cache Hit** (endereço já presente)
  - 🟥 **Cache Miss** (endereço ausente ou substituído)
  - 🟨 **Linha da cache vazia**

---

## 🧰 Estrutura do Código

### Classe `Cache`

| Método | Descrição |
|--------|-----------|
| `__init__` | Inicializa a Cache e a RAM |
| `popularRam()` | Preenche a RAM com valores aleatórios e define a linha da cache correspondente ao endereço da RAM |
| `inicializarCache()` | Prepara a cache com linhas vazias |
| `buscarEndereco(endereco, valorNovo)` | Simula acesso à cache para um endereço específico atribuindo/sobrescrevendo um novo valor à aquele endereço |
| `printRam()` | Exibe a RAM formatada no terminal |
| `printCache()` | Exibe a Cache formatada no terminal |

---

## 📊 Exemplo de Saída

```text
           RAM
Endereço | Linha | Valor
------------------------
   0     |   0   |  56  
   1     |   1   |  23  
   2     |   2   |  67  
   3     |   0   |  56  
   4     |   1   |  16  
   5     |   2   |  67
   6     |   0   |  56  
   7     |   1   |  23  
   8     |   2   |  99   

           Cache
Linha | Endereço | Valor
------------------------
  0   |    -     |   -  
  1   |    -     |   -  
  2   |    -     |   -  

Buscando endereço: 8     --> Procurando o endereço 8 na Cache
RESULTADO: Linha da cache vazia!

           Cache
Linha | Endereço | Valor
------------------------
  0   |    -     |   -  
  1   |    -     |   - 
  2   |    8     |  99   --> Endereço 8 definido na Cache

Buscando endereço: 8     --> Procurando o endereço 8 na Cache
RESULTADO: Cache hit na linha 2
