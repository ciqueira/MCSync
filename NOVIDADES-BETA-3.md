# MCSync v0.1.0 Beta 3

A Beta 3 consolida a identidade pública do MCSync e melhora a transparência da
conexão com o Google Drive. O fluxo de transferência permanece baseado nas
funções introduzidas na Beta 2.

## Principais mudanças

- O aplicativo, os menus, o pacote DMG e os documentos incorporados agora usam
  o nome público **MCSync**.
- O arquivo distribuído passa a ser
  `MCSync-0.1.0-beta.3-arm64.dmg`.
- **Read-only** é o acesso inicial padrão ao conectar o Google Drive.
- **Read & write** continua disponível quando o usuário precisa enviar, criar
  ou atualizar conteúdo no Drive.
- A ação de conexão passa a ser identificada como **Connect Google Drive**.
- A caixa de conexão informa que os dados do Google Drive são processados
  localmente no Mac.
- A política de privacidade pode ser aberta diretamente pela caixa de conexão.
- Site, política de privacidade e identidade visual foram alinhados ao nome
  MCSync.

## Transferências

A Beta 3 mantém as funções da Beta 2:

- Local → Local, Local → Google Drive e Google Drive → Local;
- filtros de conteúdo e inclusão opcional de subpastas;
- estruturas de destino, pasta com data e caminho final antecipado;
- análise de dados e espaço disponível antes da fila;
- retomada, verificação de integridade e resumo de conclusão;
- até duas operações simultâneas;
- rclone 1.74.4 incorporado, sem dependência do Homebrew.

Consulte as [novidades da Beta 2](https://github.com/ciqueira/MCSync/blob/main/NOVIDADES-BETA-2.md)
para a lista detalhada dessas funções.

## Instalação no macOS

Esta beta é compatível com Macs Apple Silicon e macOS 14.6 ou mais recente.
Ela ainda não possui notarização Apple. Se o macOS bloquear a primeira
abertura, use **System Settings > Privacy & Security > Open Anyway**.

Se o aplicativo continuar bloqueado, abra o Terminal e execute:

```bash
xattr -cr /Applications/MCSync.app
```

## Google Drive

Os modos **Read-only** e **Read & write** solicitam somente o acesso escolhido
durante a conexão. Enquanto a verificação pública do OAuth não estiver
concluída, o Google poderá mostrar um aviso de aplicativo não verificado.

Os arquivos são transferidos diretamente entre o Mac e o Google Drive. Tokens
OAuth ficam armazenados localmente em uma configuração criptografada do
rclone. Consulte a [Política de Privacidade](https://sync.mcnexus.app/privacy/).

## Limitações conhecidas

- Compatível somente com Macs Apple Silicon.
- Requer macOS 14.6 ou mais recente.
- Ainda não possui assinatura Developer ID nem notarização Apple.
- Esta é uma versão de avaliação. Use cópias não críticas e mantenha a origem
  até confirmar o resultado.

Antes do primeiro teste, consulte o [Guia rápido](https://github.com/ciqueira/MCSync/blob/main/GUIA-RAPIDO.md).
