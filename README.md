# **Manipulação de Strings e Uso de Metacaracteres em JavaScript**

Este documento aborda os principais métodos de manipulação de strings no JavaScript, bem como o uso de metacaracteres em expressões regulares para busca e formatação avançada de strings.

## **1. Principais Métodos de Strings no JavaScript**

### 1.1 **`length`**

- Retorna o tamanho da string (número de caracteres).

   ```javascript
   const texto = "JavaScript";
   console.log(texto.length); // 10
   ```

### 1.2 **`toUpperCase()` e `toLowerCase()`**

- Convertem a string para maiúsculas e minúsculas, respectivamente.

   ```javascript
   const texto = "JavaScript";
   console.log(texto.toUpperCase()); // "JAVASCRIPT"
   console.log(texto.toLowerCase()); // "javascript"
   ```

### 1.3 **`trim()`**

- Remove os espaços em branco do início e do fim da string.

   ```javascript
   const texto = "   JavaScript   ";
   console.log(texto.trim()); // "JavaScript"
   ```

### 1.4 **`indexOf()` e `lastIndexOf()`**

- Retornam o índice da primeira e última ocorrência de um caractere ou substring. Retorna `-1` se não encontrado.

   ```javascript
   const texto = "JavaScript é ótimo";
   console.log(texto.indexOf("a")); // 1
   console.log(texto.lastIndexOf("a")); // 3
   ```

### 1.5 **`slice()`**

- Extrai uma parte da string e retorna como uma nova string. Aceita índices negativos para contar de trás para frente.

   ```javascript
   const texto = "JavaScript";
   console.log(texto.slice(0, 4)); // "Java"
   console.log(texto.slice(-6)); // "Script"
   ```

### 1.6 **`substring()`**

- Similar ao `slice()`, mas não aceita índices negativos.

   ```javascript
   const texto = "JavaScript";
   console.log(texto.substring(0, 4)); // "Java"
   ```

### 1.7 **`replace()`**

- Substitui uma parte da string por outra. Substitui apenas a primeira ocorrência, a menos que um regex global seja usado.

   ```javascript
   const texto = "JavaScript é ótimo";
   console.log(texto.replace("ótimo", "incrível")); // "JavaScript é incrível"
   ```

### 1.8 **`replace()` com Regex Global**

- Usa uma expressão regular com a flag `g` para substituir todas as ocorrências de uma substring na string.

   ```javascript
   const texto = "JavaScript é popular. JavaScript é versátil.";
   const novoTexto = texto.replace(/JavaScript/g, "JS");
   console.log(novoTexto); // "JS é popular. JS é versátil."
   ```

- **Explicação:** O regex `/JavaScript/g` busca todas as ocorrências da palavra "JavaScript" e substitui por "JS".

### 1.9 **`split()`**

- Divide a string com base em um separador e retorna um array de substrings.

   ```javascript
   const texto = "JavaScript,HTML,CSS";
   console.log(texto.split(",")); // ["JavaScript", "HTML", "CSS"]
   ```

### 1.10 **`includes()`**

- Verifica se uma string contém uma substring específica, retornando `true` ou `false`.

   ```javascript
   const texto = "JavaScript é ótimo";
   console.log(texto.includes("ótimo")); // true
   ```

### 1.11 **`startsWith()` e `endsWith()`**

- Verificam se a string começa ou termina com uma substring específica.

   ```javascript
   const texto = "JavaScript";
   console.log(texto.startsWith("Java")); // true
   console.log(texto.endsWith("Script")); // true
   ```

### 1.12 **`charAt()`**

- Retorna o caractere de uma string em um índice especificado.

   ```javascript
   const texto = "JavaScript";
   console.log(texto.charAt(4)); // "S"
   ```

### 1.13 **`concat()`**

- Concatena duas ou mais strings.

   ```javascript
   const texto1 = "Java";
   const texto2 = "Script";
   console.log(texto1.concat(texto2)); // "JavaScript"
   ```

---

## **2. Uso de Metacaracteres em JavaScript com Exemplos**

### 2.1 **`\d` e `\D`**

- **`\d`**: Corresponde a qualquer dígito (0-9).
  
  **Exemplo:**

  ```javascript
  const texto = "Endereço: Rua 123, Número 456";
  const digitos = texto.match(/\d+/g);
  console.log(digitos); // ["123", "456"]
  ```

- **`\D`**: Corresponde a qualquer caractere que não seja um dígito.
  
  **Exemplo:**

  ```javascript
  const texto = "Endereço: Rua 123, Número 456";
  const naoDigitos = texto.match(/\D+/g);
  console.log(naoDigitos); // ["Endereço: Rua ", ", Número "]
  ```

### 2.2 **`\w` e `\W`**

- **`\w`**: Corresponde a qualquer caractere alfanumérico (letras, números e sublinhado).
  
  **Exemplo:**

  ```javascript
  const texto = "User_123!@#";
  const alfanumericos = texto.match(/\w+/g);
  console.log(alfanumericos); // ["User_123"]
  ```

- **`\W`**: Corresponde a qualquer caractere que não seja alfanumérico.
  
  **Exemplo:**

  ```javascript
  const texto = "User_123!@#";
  const naoAlfanumericos = texto.match(/\W+/g);
  console.log(naoAlfanumericos); // ["!@#"]
  ```

### 2.3 **`\s` e `\S`**

- **`\s`**: Corresponde a qualquer espaço em branco (espaço, tabulação, quebra de linha).
  
  **Exemplo:**

  ```javascript
  const texto = "Hello\tWorld\nJavaScript!";
  const espacos = texto.match(/\s/g);
  console.log(espacos); // ["\t", "\n"]
  ```

- **`\S`**: Corresponde a qualquer caractere que não seja um espaço em branco.
  
  **Exemplo:**

  ```javascript
  const texto = "Hello\tWorld\nJavaScript!";
  const naoEspacos = texto.match(/\S+/g);
  console.log(naoEspacos); // ["Hello", "World", "JavaScript!"]
  ```

### 2.4 **`^` e `$`**

- **`^`**: Indica o início de uma string ou linha.
  
  **Exemplo:**

  ```javascript
  const texto = "Hello World";
  const inicio = /^Hello/.test(texto);
  console.log(inicio); // true
  ```

- **`$`**: Indica o final de uma string ou linha.
  
  **Exemplo:**

  ```javascript
  const texto = "Hello World";
  const final = /World$/.test(texto);
  console.log(final); // true
  ```

### 2.5 **`.` (Ponto)**

- **Descrição**: Corresponde a qualquer caractere, exceto quebras de linha.
  
  **Exemplo:**

  ```javascript
  const texto = "H.llo";
  const correspondencia = /H.llo/.test(texto);
  console.log(correspondencia); // true
  ```

### 2.6 **`*`, `+`, e `?`**

- **`*`**: Corresponde ao caractere anterior zero ou mais vezes.
  
  **Exemplo:**

  ```javascript
  const texto = "aaaab";
  const resultado = texto.match(/a*/g);
  console.log(resultado); // ["aaaa", ""]
  ```

- **`+`**: Corresponde ao caractere anterior uma ou mais vezes.
  
  **Exemplo:**

  ```javascript
  const texto = "aaaab";
  const resultado = texto.match(/a+/g);
  console.log(resultado); // ["aaaa"]
  ```

- **`?`**: Corresponde ao caractere anterior zero ou uma vez.
  
  **Exemplo:**

  ```javascript
  const texto = "color colour";
  const resultado = texto.match(/colou?r/g);
  console.log(resultado); // ["color", "colour"]
  ```

### 2.7 **`[]` (Classes de Caracteres)**

- **Descrição**: Define um conjunto de caracteres para corresponder.
  
  **Ex

emplo:**

  ```javascript
  const texto = "a1b2c3";
  const resultado = texto.match(/[abc]/g);
  console.log(resultado); // ["a", "b", "c"]
  ```

### 2.8 **`|` (Operador OR)**

- **Descrição**: Corresponde ao padrão à esquerda ou à direita.
  
  **Exemplo:**

  ```javascript
  const texto = "cat dog";
  const resultado = texto.match(/cat|dog/g);
  console.log(resultado); // ["cat", "dog"]
  ```

### 2.9 **`()` (Grupos de Captura)**

- **Descrição**: Agrupa parte da expressão regular para captura e referência.
  
  **Exemplo:**

  ```javascript
  const texto = "2023-09-22";
  const resultado = texto.replace(/(\d{4})-(\d{2})-(\d{2})/, '$3/$2/$1');
  console.log(resultado); // "22/09/2023"
  ```

### 2.10 **`\b` e `\B` (Limites de Palavra)**

- **`\b`**: Corresponde a um limite de palavra.
  
  **Exemplo:**

  ```javascript
  const texto = "word wordy";
  const resultado = texto.match(/\bword\b/g);
  console.log(resultado); // ["word"]
  ```

- **`\B`**: Corresponde a qualquer posição que não seja um limite de palavra.
  
  **Exemplo:**

  ```javascript
  const texto = "word wordy";
  const resultado = texto.match(/\Bword\B/g);
  console.log(resultado); // []
  ```

### 2.11 **`{}` (Quantificadores)**

- **Descrição**: Especifica um número exato ou intervalo de repetições.
  
  **Exemplo:**

  ```javascript
  const texto = "aaaabb";
  const resultado = texto.match(/a{2,3}/g);
  console.log(resultado); // ["aaa", "aa"]
  ```
