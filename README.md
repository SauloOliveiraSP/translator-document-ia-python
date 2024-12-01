
# Tradução de Documentos com IA Generativa da Azure
Este projeto utiliza a **API Translator** da Azure para traduzir textos e documentos do formato `.docx` para o idioma desejado.

---

## Requisitos

1. **Python**  
   Instale as bibliotecas necessárias com o seguinte comando:
   ```bash
   pip install requests python-docx
   ```
   
2. **Serviço de IA Generativa na Azure**  
   - Crie um **Serviço Translator** no portal da Azure.
   - Anote as seguintes informações:
     - `subscription_key`: Chave de assinatura gerada.
     - `endpoint`: URL do endpoint fornecida pelo serviço.
     - `location`: Região na qual o serviço foi configurado.

---

## Variáveis do Código

- **`subscription_key`**: Chave de acesso ao serviço Translator.
- **`endpoint`**: URL base do serviço Translator.
- **`location`**: Região onde o serviço foi configurado.
- **`language_destination`**: Define o idioma para o qual o texto será traduzido. Exemplos:
  - `pt-br` para Português-BR
  - `es` para Espanhol

---

## Explicação do Código

1. **Função `translator_text`**  
   - Recebe um texto e o idioma de destino.
   - Constrói a URL do endpoint com o caminho `/translate`.
   - Envia uma requisição POST ao Translator API com os parâmetros necessários.
   - Retorna o texto traduzido.

2. **Função `traslate_document`**  
   - Abre um arquivo `.docx` e lê seu conteúdo.
   - Traduz cada parágrafo utilizando a função `translator_text`.
   - Cria um novo documento traduzido e salva com um sufixo indicando o idioma.

---

## Exemplo de Uso

1. Traduz o texto `"Hello World!"` para o idioma configurado na variável `language_destination`.
2. Traduz um arquivo chamado `musica.docx`.

---

## Observações

1. **Permissões de Rede**  
   Certifique-se de que sua máquina tenha acesso à internet e à API do Azure.

2. **Configuração Inicial**  
   Substitua `subscription_key`, `endpoint` e `location` pelos valores fornecidos ao criar o serviço na Azure.

3. **Limitações de API**  
   Verifique as restrições de uso (limite de requisições) em sua assinatura do Azure.

4. **Formato de Idiomas**  
   Certifique-se de que o idioma desejado está no formato correto (`pt-br`, `es`, etc.).

5. **Saída dos Arquivos**  
   O arquivo traduzido será salvo no mesmo diretório do original com um sufixo indicando o idioma.  
   Exemplo: `musica.docx` será salvo como `musica_pt-br.docx`.
