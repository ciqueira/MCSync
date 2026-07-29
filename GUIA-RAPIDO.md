# MCSync — Guia rápido de uso

## 1. Conecte o Google Drive

Se a transferência utilizar o Drive:

1. Clique no cabeçalho **Google Drive**.
2. Escolha **Read-only** para baixar ou **Read & write** para baixar e enviar.
3. Clique em **Connect** e autorize a conta no navegador.

Quando não houver Google Drive na operação, esta etapa não é necessária.

## 2. Escolha origem e destino

Em **Source**, escolha a pasta que será copiada.

Em **Destination**, escolha a pasta que receberá os arquivos.

- **Local:** SSD ou pasta disponível no Mac.
- **Remote:** Google Drive.
- **Choose Folder…:** abre o seletor de pastas.

No seletor do Drive, use **Select** para escolher uma pasta sem entrar nela ou
**Select Current Folder** para escolher a pasta aberta.

## 3. Escolha a estrutura das pastas

- **Include subfolders:** inclui as subpastas da origem.
- **Create source folder:** cria no destino uma pasta com o nome da origem.
- **Preserve source path:** recria o caminho completo da origem no destino.

Para o uso mais simples, mantenha **Include subfolders** e
**Create source folder** marcados.

## 4. Analise a transferência

Clique em **Analyze Transfer**.

O app mostrará:

- total da pasta de origem;
- quantidade que precisa ser transferida;
- espaço livre no destino;
- possíveis avisos.

Se o destino não tiver espaço suficiente, a informação aparecerá em vermelho.

## 5. Use as configurações recomendadas

Para os primeiros testes, mantenha:

| Controle | Recomendado |
|---|---|
| **Mode** | Copy / Update |
| **Verification** | MD5 |
| **Performance** | Balanced |

**Copy / Update** copia arquivos novos ou alterados e não apaga arquivos
extras do destino.

## 6. Adicione à fila

Clique em **Add to Queue**.

A primeira operação começa automaticamente. As próximas aguardam em
**Waiting**, seguindo a ordem em que foram adicionadas.

É possível usar **Start in Parallel** para executar uma segunda operação ao
mesmo tempo.

## 7. Acompanhe a operação

| Controle | Ação |
|---|---|
| **Pause** | Pausa para continuar depois. |
| **Resume** | Continua uma operação pausada. |
| **Cancel** | Cancela sem apagar a origem. |
| **Retry** | Tenta novamente uma operação com falha. |

Durante a cópia, o item mostra progresso, velocidade, tempo estimado e os
arquivos atuais.

## 8. Confira o resultado

- **Succeeded:** operação concluída corretamente.
- **Succeeded with warnings:** concluída, mas existem avisos para conferir.
- **Failed:** a operação não foi concluída.
- **Cancelled:** a operação foi cancelada.

Quando o resultado for **Succeeded**, confira as estatísticas de arquivos,
dados transferidos e verificação.

Mantenha a pasta de origem quando houver avisos ou falhas.

## Controles rápidos

| Controle | Uso |
|---|---|
| **Analyze Transfer** | Analisa sem copiar arquivos. |
| **Swap** | Inverte Source e Destination. |
| **Clear Folders** | Limpa as duas pastas selecionadas. |
| **Add to Queue** | Adiciona e inicia a operação quando a fila está livre. |
| **Clear History** | Limpa o histórico, sem apagar arquivos transferidos. |

