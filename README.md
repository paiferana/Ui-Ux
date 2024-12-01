# CódigoTestes
# Análise de Código: Teste de Caixa Branca (Estático)

## Descrição do Projeto
Este repositório contém um código exemplo para realizar um teste de caixa branca estático, apontando erros e vulnerabilidades no código original.

## Erros Encontrados
1. **SQL Injection**
   - O uso de concatenação de strings para construir a query SQL (`+`) torna o código vulnerável a ataques.
   - **Correção:** Usar `PreparedStatement` para evitar injeções.

2. **Credenciais no Código**
   - Usuário e senha do banco de dados estão embutidos no código.
   - **Correção:** Usar variáveis de ambiente ou arquivos de configuração seguros.

3. **Classe do Driver**
   - Classe do driver foi declarada incorretamente:
     ```java
     Class.forName("com.mysql.Driver.Manager").newInstance();
     ```
   - **Correção:** Usar o driver correto:
     ```java
     Class.forName("com.mysql.cj.jdbc.Driver");
     ```

4. **Gerenciamento de Recursos**
   - Conexões, Statements e ResultSets não são fechados.
   - **Correção:** Usar `try-with-resources`.

5. **Exceções Ignoradas**
   - Exceções capturadas no código são ignoradas, dificultando o diagnóstico de erros.
   - **Correção:** Registrar as exceções para análise.

6. **Variáveis Públicas**
   - Variáveis `nome` e `result` são públicas.
   - **Correção:** Torná-las privadas e usar métodos getter e setter.

## Como Rodar o Código
1. Configure o banco de dados MySQL e crie a tabela `usuarios`.
2. Ajuste as credenciais no código para acessar o banco.
3. Compile e execute o programa.

## Como Contribuir
Sinta-se à vontade para criar issues ou pull requests com melhorias.
