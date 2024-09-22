# **Principais Métodos de Strings no JavaScript**

## 1. **`length`**
   - Retorna o tamanho da string (número de caracteres).
   ```javascript
   const texto = "JavaScript";
   console.log(texto.length); // 10
   ```

## 2. **`toUpperCase()` e `toLowerCase()`**
   - Convertem a string para maiúsculas e minúsculas, respectivamente.
   ```javascript
   const texto = "JavaScript";
   console.log(texto.toUpperCase()); // "JAVASCRIPT"
   console.log(texto.toLowerCase()); // "javascript"
   ```

## 3. **`trim()`**
   - Remove os espaços em branco do início e do fim da string.
   ```javascript
   const texto = "   JavaScript   ";
   console.log(texto.trim()); // "JavaScript"
   ```

## 4. **`indexOf()` e `lastIndexOf()`**
   - Retornam o índice da primeira e última ocorrência de um caractere ou substring. Retorna `-1` se não encontrado.
   ```javascript
   const texto = "JavaScript é ótimo";
   console.log(texto.indexOf("a")); // 1
   console.log(texto.lastIndexOf("a")); // 3
   ```

## 5. **`slice()`**
   - Extrai uma parte da string e retorna como uma nova string. Aceita índices negativos para contar de trás para frente.
   ```javascript
   const texto = "JavaScript";
   console.log(texto.slice(0, 4)); // "Java"
   console.log(texto.slice(-6)); // "Script"
   ```

## 6. **`substring()`**
   - Similar ao `slice()`, mas não aceita índices negativos.
   ```javascript
   const texto = "JavaScript";
   console.log(texto.substring(0, 4)); // "Java"
   ```

## 7. **`replace()`**
   - Substitui uma parte da string por outra. Substitui apenas a primeira ocorrência, a menos que um regex global seja usado.
   ```javascript
   const texto = "JavaScript é ótimo";
   console.log(texto.replace("ótimo", "incrível")); // "JavaScript é incrível"
   ```

## 8. **`replace()` com Regex Global**
   - Usa uma expressão regular com a flag `g` para substituir todas as ocorrências de uma substring na string.
   ```javascript
   const texto = "JavaScript é popular. JavaScript é versátil.";
   // Usando regex com flag global 'g' para substituir todas as ocorrências
   const novoTexto = texto.replace(/JavaScript/g, "JS");
   console.log(novoTexto); // "JS é popular. JS é versátil."
   ```
   - **Explicação:** O regex `/JavaScript/g` busca todas as ocorrências da palavra "JavaScript" e substitui por "JS".

## 9. **`split()`**
   - Divide a string com base em um separador e retorna um array de substrings.
   ```javascript
   const texto = "JavaScript,HTML,CSS";
   console.log(texto.split(",")); // ["JavaScript", "HTML", "CSS"]
   ```

## 10. **`includes()`**
   - Verifica se uma string contém uma substring específica, retornando `true` ou `false`.
   ```javascript
   const texto = "JavaScript é ótimo";
   console.log(texto.includes("ótimo")); // true
   ```

## 11. **`startsWith()` e `endsWith()`**
   - Verificam se a string começa ou termina com uma substring específica.
   ```javascript
   const texto = "JavaScript";
   console.log(texto.startsWith("Java")); // true
   console.log(texto.endsWith("Script")); // true
   ```

## 12. **`charAt()`**
   - Retorna o caractere de uma string em um índice especificado.
   ```javascript
   const texto = "JavaScript";
   console.log(texto.charAt(4)); // "S"
   ```

## 13. **`concat()`**
   - Concatena duas ou mais strings.
   ```javascript
   const texto1 = "Java";
   const texto2 = "Script";
   console.log(texto1.concat(texto2)); // "JavaScript"
   ```

### **Conclusão**
Esses métodos são fundamentais para manipular e transformar strings em JavaScript. Lembre-se que todos esses métodos não alteram a string original, mas retornam uma nova string modificada. Para "salvar" a modificação, é necessário atribuir o resultado a uma variável.

Se precisar de mais detalhes sobre algum método ou exemplos específicos, é só me avisar!
