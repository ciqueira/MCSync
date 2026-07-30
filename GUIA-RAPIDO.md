# MCSync — Guia rápido de uso

## 1. Instale o aplicativo

1. Abra o arquivo DMG.
2. Arraste o MCSyncDrive para **Applications**.
3. Tente abrir o aplicativo.
4. Se o macOS bloquear, abra **System Settings > Privacy & Security** e use
   **Open Anyway**.

O MCSyncDrive já inclui o rclone. Não é necessário instalar Homebrew.

## 2. Conecte o Google Drive

Esta etapa só é necessária quando a origem ou o destino estiver no Drive:

1. Clique no cabeçalho **Google Drive**.
2. Escolha **Read-only** para baixar ou **Read & write** para baixar e enviar.
3. Clique em **Connect** e autorize a conta no navegador.

Enquanto o OAuth estiver em modo Testing, a conta precisa estar cadastrada
como testadora e o Google poderá solicitar uma nova conexão depois de sete
dias.

## 3. Escolha origem e destino

Em **Source**, escolha a pasta que será copiada. Em **Destination**, escolha a
pasta que receberá os arquivos.

- **Local:** SSD ou pasta disponível no Mac.
- **Remote:** Google Drive.
- **Include subfolders:** inclui as subpastas da origem.
- **Content:** filtra todos os arquivos, fotos, fotos e vídeos ou mídias com
  sidecars.

No seletor do Drive, use **Select** para escolher uma pasta sem entrar nela,
**Select Current Folder** para escolher a pasta aberta ou **New Folder** para
criar uma pasta no destino.

## 4. Defina a organização do destino

Escolha uma opção de **Destination structure**:

- **Keep source subfolders:** mantém as pastas abaixo da origem.
- **Create source folder:** cria no destino uma pasta com o nome da origem.
- **Preserve full source path:** recria o caminho completo da origem.
- **Flatten into destination (Keep both):** coloca os arquivos diretamente no
  destino e adiciona numeração quando houver nomes iguais.

Ative **Dated folder** para criar antes da estrutura uma pasta com a data atual
no formato `yyyyMMdd`.

Confira **Final destination** antes de continuar. Em destinos locais, o
prefixo `/Volumes/` é omitido apenas na tela para facilitar a leitura.

## 5. Analise a transferência

Clique em **Analyze Transfer** para conferir:

- total e quantidade de arquivos da origem;
- dados que realmente precisam ser transferidos;
- espaço livre no destino;
- possíveis avisos.

Use **Stop Analysis** para interromper a análise. Se faltar espaço, o app
mostrará o aviso em vermelho antes de adicionar a operação.

## 6. Confira as configurações

Para os primeiros testes, mantenha:

| Controle | Recomendado |
|---|---|
| **Performance** | Balanced |
| **Mode** | Copy / Update |
| **Verification** | MD5 |

**Mode** e **Verification** ficam dentro de **Advanced settings**. O cabeçalho
recolhido mostra as escolhas atuais.

**Copy / Update** copia arquivos novos ou alterados e não apaga arquivos
extras do destino.

## 7. Adicione à fila

Clique em **Add to Queue**. A operação começa quando houver uma posição livre.

As próximas operações ficam em **Waiting**, seguindo a ordem da fila.
**Start in Parallel** permite executar uma segunda operação ao mesmo tempo.

## 8. Acompanhe a operação

| Controle | Ação |
|---|---|
| **Pause** | Pausa para continuar depois. |
| **Resume** | Continua uma operação pausada. |
| **Cancel** | Cancela sem apagar a origem. |
| **Retry** | Tenta novamente uma operação com falha. |

Durante a cópia, o item mostra progresso, velocidade, tempo estimado e os
arquivos atuais.

## 9. Confira o resultado

Quando a operação terminar com **Succeeded**, o resumo mostrará em uma linha:

- **Processing time**;
- **Data transferred**;
- **Files transferred**;
- **Integrity check**.

**Succeeded with warnings** indica que existem avisos para conferir.
Em **Failed** ou **Cancelled**, mantenha a origem e revise a operação antes de
tentar novamente.

## Controles rápidos

| Controle | Uso |
|---|---|
| **Analyze Transfer** | Analisa sem copiar arquivos. |
| **Swap** | Inverte Source e Destination. |
| **Clear Folders** | Limpa as duas pastas selecionadas. |
| **Add to Queue** | Adiciona a operação à fila. |
| **Clear History** | Limpa histórico, estatísticas e artefatos da operação. |
