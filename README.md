# MCSync

Transfira projetos entre SSDs e Google Drive com análise de espaço, retomada e
verificação de integridade.

- Site: [sync.mcnexus.app](https://sync.mcnexus.app/)
- Privacidade: [sync.mcnexus.app/privacy](https://sync.mcnexus.app/privacy/)

O MCSync foi criado para tornar cópias grandes mais simples de acompanhar e
mais fáceis de conferir ao final. Este repositório reúne os instaladores e a
documentação pública da versão beta.

## Beta 2

A Beta 2 melhora a preparação e a conferência das operações:

- filtros para copiar todos os arquivos, fotos, vídeos ou mídias com sidecars;
- novas opções de estrutura e organização do destino;
- pasta opcional com data no formato `yyyyMMdd`;
- caminho final do destino visível antes de adicionar à fila;
- configurações avançadas recolhidas em uma seção própria;
- resumo de conclusão mais claro, com quatro estatísticas;
- criação e seleção de pastas diretamente no seletor do Google Drive.

Consulte as [novidades da Beta 2](NOVIDADES-BETA-2.md) para conhecer os
detalhes e as limitações desta avaliação.

## Download

Baixe o DMG mais recente na página de
[Releases](https://github.com/ciqueira/MCSync/releases).

Esta beta é compatível com Macs Apple Silicon e macOS 14.6 ou mais recente.
O aplicativo inclui o rclone e não requer Homebrew.

## Instalação no macOS

Esta beta ainda não é notarizada pela Apple.

1. Abra o arquivo `.dmg` e arraste `MCSync.app` para `/Applications`.
2. Inicie o MCSync.
3. Se o macOS bloquear o aplicativo, abra **System Settings > Privacy &
   Security** e clique em **Open Anyway**.

Se o aplicativo continuar bloqueado e tiver sido baixado da página oficial de
Releases do MCSync, execute:

```bash
xattr -dr com.apple.quarantine /Applications/MCSync.app
```

Inicie o MCSync novamente. Esse comando remove somente o atributo de quarentena
do pacote do MCSync; ele não desativa o Gatekeeper globalmente.

## Guia rápido

Consulte o [Guia rápido de uso](GUIA-RAPIDO.md) antes do primeiro teste.

> O MCSync ainda não possui notarização Apple. Use cópias de arquivos não
> críticos durante a avaliação e mantenha a origem até confirmar o resultado.
