# MCSync

Transfira projetos entre SSDs e Google Drive com análise de espaço, retomada e
verificação de integridade.

- Site: [sync.mcnexus.app](https://sync.mcnexus.app/)
- Privacidade: [sync.mcnexus.app/privacy](https://sync.mcnexus.app/privacy/)

O MCSync foi criado para tornar cópias grandes mais simples de acompanhar e
mais fáceis de conferir ao final. Este repositório reúne os instaladores e a
documentação pública da versão beta.

## Beta 3

A Beta 3 consolida o nome público MCSync e torna a conexão com o Google Drive
mais clara:

- aplicativo, menus, DMG e documentação identificados como **MCSync**;
- **Read-only** definido como acesso inicial padrão ao Google Drive;
- acesso **Read & write** disponível somente quando selecionado pelo usuário;
- ação **Connect Google Drive** com identificação mais direta;
- aviso de processamento local e link para a política de privacidade dentro da
  caixa de conexão;
- site, política e identidade visual alinhados ao aplicativo.

As funções de transferência introduzidas na Beta 2 permanecem disponíveis.
Consulte as [novidades da Beta 3](NOVIDADES-BETA-3.md) para conhecer os
detalhes e as limitações desta avaliação.

## Download

Baixe o [MCSync v0.1.0 Beta 3](https://github.com/ciqueira/MCSync/releases/tag/v0.1.0-beta.3)
ou consulte a página de [Releases](https://github.com/ciqueira/MCSync/releases).

Esta beta é compatível com Macs Apple Silicon e macOS 14.6 ou mais recente.
O aplicativo inclui o rclone e não requer Homebrew.

## Instalação no macOS

Esta beta ainda não é notarizada pela Apple.

1. Abra o arquivo `.dmg` e arraste `MCSync.app` para `/Applications`.
2. Inicie o MCSync.
3. Se o macOS bloquear o aplicativo, abra **System Settings > Privacy &
   Security** e clique em **Open Anyway**.

Se o aplicativo continuar bloqueado, abra o Terminal e execute:

```bash
xattr -cr /Applications/MCSync.app
```

Inicie o MCSync novamente.

## Guia rápido

Consulte o [Guia rápido de uso](GUIA-RAPIDO.md) antes do primeiro teste.

> O MCSync ainda não possui notarização Apple. Use cópias de arquivos não
> críticos durante a avaliação e mantenha a origem até confirmar o resultado.
