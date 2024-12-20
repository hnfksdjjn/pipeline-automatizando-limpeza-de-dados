# pipeline-automatizando-limpeza-de-dados

# Data Processing Pipeline

Este projeto é um pipeline de processamento de dados, projetado para carregar, limpar, formatar e salvar dados de um arquivo CSV. Ele usa o **pandas** para manipulação de dados e a biblioteca **logging** para monitorar o processo. O pipeline realiza várias etapas, incluindo o tratamento de valores ausentes, remoção de duplicatas, normalização de dados e formatação para melhorar a legibilidade.

## Funcionalidades

O pipeline é composto pelas seguintes etapas:

### 1. **Carregar Dados**
   - Função: `load_data(file_path, delimiter=";")`
   - Carrega os dados de um arquivo CSV usando o delimitador especificado (por padrão, `;`).
   - Em caso de erro, registra uma mensagem no log.

### 2. **Tratar Valores Ausentes**
   - Função: `handle_missing_values(df, strategy="mean")`
   - Trata valores ausentes no DataFrame usando uma das estratégias: 'mean', 'median', 'mode', ou 'drop'.

### 3. **Remover Duplicatas**
   - Função: `handle_duplicates(df, subset=None, keep="first")`
   - Remove duplicatas do DataFrame, com a opção de escolher quais duplicatas manter.

### 4. **Normalizar Colunas Numéricas**
   - Função: `normalize_columns(df)`
   - Normaliza os valores nas colunas numéricas para o intervalo [0, 1].

### 5. **Renomear Colunas**
   - Função: `rename_columns(df, columns_dict)`
   - Renomeia as colunas do DataFrame para nomes mais legíveis usando um dicionário de mapeamento.

### 6. **Formatar Dados**
   - Função: `format_data(df)`
   - Melhora a formatação dos dados para facilitar a leitura, incluindo:
     - Arredondamento de colunas numéricas para 2 casas decimais.
     - Conversão de valores de sexo para formatos legíveis.
     - Formatação de colunas como porcentagem.

### 7. **Exibir Dados Formatados**
   - Função: `display_formatted_data(df)`
   - Exibe os primeiros registros do DataFrame de forma legível.

### 8. **Salvar Dados**
   - Função: `save_data(df, output_path)`
   - Salva o DataFrame formatado em um arquivo CSV no caminho especificado.

## Como Usar

1. **Instale as dependências:**
   - `pandas`: Para manipulação de dados.
   - `IPython`: Para exibir os dados de forma mais legível.

2. **Configuração do arquivo de entrada:**
   - Coloque seus dados no formato CSV e ajuste o caminho do arquivo na variável `file_path`.

3. **Executar o pipeline:**
   - Chame a função `main_pipeline(file_path, output_path)` passando o caminho do arquivo CSV de entrada e o caminho do arquivo CSV de saída.

Exemplo de execução:

```python
file_path = "dados.csv"  # Substitua pelo caminho do seu arquivo CSV
output_path = "dados_limpos.csv"  # Caminho para salvar o arquivo limpo
main_pipeline(file_path, output_path)
```

## Logs

Durante a execução, o processo será monitorado por logs, permitindo acompanhar a execução do pipeline e identificar possíveis erros.

## Dependências

- `pandas`
- `IPython`

Para instalar as dependências, você pode usar o comando:

```bash
pip install pandas IPython
```

## Contribuições

Se você deseja contribuir para este projeto, sinta-se à vontade para enviar pull requests. Certifique-se de testar suas alterações e garantir que todas as funcionalidades estão funcionando corretamente.

---

Esse pipeline proporciona uma forma eficiente de processar dados de entrada, tratar problemas comuns como valores ausentes e duplicatas, e melhorar a legibilidade e a qualidade dos dados para análise posterior.
