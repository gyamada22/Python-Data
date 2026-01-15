# 9. Palindrome Number

**Data:** 09/01/2026  
**Dificuldade:** Easy  
**Tópicos:** Python, Math, Loop, Integer Manipulation  
**Link:** https://leetcode.com/problems/palindrome-number/

## Descrição
Escreva uma solução para verificar se um número inteiro é um **palíndromo**, ou seja, se ele é lido da mesma forma da esquerda para a direita e da direita para a esquerda.

Regras importantes:
- Números negativos **não são palíndromos**, pois o sinal `-` invalida a simetria.
- A solução deve funcionar sem converter o número para string.

Exemplos:
- `121` → `True`
- `-121` → `False`
- `10` → `False`

---

## Solução (Python 3)

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        # Números negativos não podem ser palíndromos
        if x < 0:
            return False
        
        num = x
        reversed_number = 0
        
        # Inverte o número usando operações matemáticas
        while num > 0:
            digit = num % 10
            reversed_number = reversed_number * 10 + digit
            num = num // 10
        
        # Compara o número original com o invertido
        return x == reversed_number
