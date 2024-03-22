# Documentação do Repositório file-connector

Este repositório contém uma aplicação MuleSoft que lida com operações de leitura, escrita e movimentação de arquivos. A aplicação inclui os seguintes fluxos:

## Fluxo `create_new_file`

Este fluxo cria um novo arquivo CSV com base nos dados recebidos em uma requisição HTTP POST. O arquivo é salvo na pasta `write/` com o nome especificado na requisição.

### Endpoints:

- `POST /writeFile`: Recebe os dados e cria um novo arquivo CSV.

## Fluxo `poll_directory_for_new_files`

Este fluxo monitora a pasta `write/` em intervalos regulares e, quando um novo arquivo é detectado, exibe informações sobre o arquivo no console.

## Fluxo `Move_file_new_folder`

Este fluxo move um arquivo da pasta `write/` para a pasta `read/` com base no nome do arquivo fornecido na requisição HTTP GET.

### Endpoints:

- `GET /moveFile/{filename}`: Move o arquivo especificado para a pasta `read/`.

## Fluxo `read_existing_files`

Este fluxo lê o conteúdo de um arquivo existente na pasta `output/` com base no nome do arquivo fornecido na requisição HTTP GET.

### Endpoints:

- `GET /readFiles/{fileName}`: Lê o conteúdo do arquivo especificado na pasta `output/`.

## Fluxo `list_files_and_folders`

Este fluxo lista todos os arquivos e pastas na pasta `output/` e exibe o tipo de cada item.

### Endpoints:

- `GET /listFiles`: Lista todos os arquivos e pastas na pasta `output/`.

---

Certifique-se de configurar adequadamente as referências de configuração, como `HTTP_Listener_config` e `File_Config`, antes de executar a aplicação.
