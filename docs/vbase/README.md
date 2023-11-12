# Documentação Técnica da API VBase VTEX

## Visão Geral

A API VBase da VTEX oferece funcionalidades para gerenciar buckets da AWS, permitindo operações como leitura, escrita, exclusão e gerenciamento de conflitos de arquivos.

Collection Postman: https://www.postman.com/birnayt/workspace/community-vtex-collection/collection/27001779-91a899ca-1d77-4e01-924b-2148ef4645a0?action=share&creator=27001779

## Autenticação

Todas as requisições devem incluir um cabeçalho de autorização com um token válido: `Authorization: Bearer [TOKEN]`.

## Endpoints

### 1. getBucket

Obtém informações de um bucket específico.

```bash
curl -X GET 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]' -H 'Authorization: Bearer [TOKEN]'
```

### 2. resetBucket

Deleta todos os arquivos de um bucket.

```bash
curl -X DELETE 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files' -H 'Authorization: Bearer [TOKEN]'
```

### 3. listFiles

Lista arquivos em um bucket.

```bash
curl -X GET 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files' -H 'Authorization: Bearer [TOKEN]'
```

### 4. getFile

Obtém um arquivo específico de um bucket.

```bash
curl -X GET 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files/[FILE_PATH]' -H 'Authorization: Bearer [TOKEN]'
```

### 5. getJSON/getRawJSON

Obtém um arquivo JSON de um bucket.

```bash
curl -X GET 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files/[FILE_PATH]' -H 'Authorization: Bearer [TOKEN]' -H 'Content-Type: application/json'
```

### 6. getFileStream

Obtém um arquivo de um bucket como um stream.

```bash
# Geralmente é feito em um contexto de programação, não com cURL.
```

### 7. saveFile/saveJSON

Salva um arquivo ou JSON em um bucket.

```bash
curl -X PUT 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files/[FILE_PATH]' -H 'Authorization: Bearer [TOKEN]' -d '[DATA]'
```

### 8. getFileMetadata

Obtém metadados de um arquivo em um bucket.

```bash
curl -X HEAD 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files/[FILE_PATH]' -H 'Authorization: Bearer [TOKEN]'
```

### 9. saveZippedContent

Salva conteúdo compactado em um bucket.

```bash
# Específico para conteúdo compactado.
```

### 10. deleteFile

Deleta um arquivo de um bucket.

```bash
curl -X DELETE 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/files/[FILE_PATH]' -H 'Authorization: Bearer [TOKEN]'
```

### 11. getConflicts

Lista conflitos em um bucket.

```bash
curl -X GET 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/conflicts' -H 'Authorization: Bearer [TOKEN]'
```

### 12. resolveConflict

Resolve um conflito específico em um bucket.

```bash
curl -X PATCH 'https://infra.io.vtex.com/vbase/v2/{{accountName}}/{{workspace}}/buckets/[APP_NAME]/[BUCKET_NAME]/conflicts' -H 'Authorization: Bearer [TOKEN]' -d '[RESOLUTION_DATA]'
```

## Notas Adicionais

- Substitua `[APP_NAME]`, `[BUCKET_NAME]`, `[FILE_PATH]`, `[TOKEN]` e `[DATA]` pelos valores correspondentes.
- Insira o nome da conta e do workspace nos locais indicados por `{{accountName}}` e `{{workspace}}`.

## Suporte e Contato

Para suporte e mais informações, entre em contato com a equipe de desenvolvimento da VTEX.
