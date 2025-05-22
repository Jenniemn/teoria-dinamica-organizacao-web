## 2. Validação de Formulários com JavaScript (Lado do Cliente)

*Captura e Verificação de Dados*

JavaScript permite interceptar o envio de formulários e validar os dados antes que eles sejam enviados ao servidor, melhorando a experiência do usuário e reduzindo a carga do servidor.

Exemplo básico de validação:

```javascript
<form onsubmit="return validarFormulario()">
  <input type="text" id="nome" placeholder="Digite seu nome">
  <input type="submit" value="Enviar">
</form>

<script>
  function validarFormulario() {
    let nome = document.getElementById("nome").value;
    if (nome === "") {
      alert("O nome é obrigatório.");
      return false; // impede o envio
    }
    return true;
  }
</script>
```
## Expressões Regulares para Validações Avançadas

As expressões regulares (regex) são padrões utilizados para testar e validar formatos de texto, como emails, números de telefone e senhas.

Exemplo: Validação de Email

```javascript
function validarEmail(email) {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return regex.test(email);
}

console.log(validarEmail("usuario@email.com")); // true
console.log(validarEmail("usuario@email"));     // false
```

*Explicação do Padrão*

`^ e $`: delimitam o início e fim da string.

`[^\s@]+`: um ou mais caracteres que não sejam espaço (\s) ou @.

`@`: caractere obrigatório.

`[^\s@]+`: domínio.

`\.`: ponto literal.

`[^\s@]+`: sufixo do domínio (como .com, .org).

*Vantagens da Validação no Cliente*

*Imediata*: feedback instantâneo ao usuário.

*Economiza recursos do servidor*: evita requisições desnecessárias.

*Melhora a UX*: reduz frustração com formulários.


