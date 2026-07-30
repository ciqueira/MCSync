# MCSyncDrive Beta 2

A Beta 2 concentra as melhorias feitas durante os primeiros testes da
interface e do fluxo de transferência.

## Principais mudanças

- Transferências Local → Local, Local → Google Drive e Google Drive → Local.
- Filtros de conteúdo para fotos, vídeos, áudio e arquivos sidecar.
- Quatro formas de organizar o destino, incluindo
  **Flatten into destination (Keep both)**.
- Pasta de destino opcional com data no formato `yyyyMMdd`.
- Exibição antecipada do caminho final que será usado pela operação.
- Criação de novas pastas dentro do seletor do Google Drive.
- Retorno do seletor à última pasta visitada.
- Análise opcional de arquivos, volume de dados e espaço livre.
- Até duas operações simultâneas, mantendo as demais na ordem da fila.
- Resumo final com tempo, dados, arquivos e verificação de integridade.
- rclone incorporado ao aplicativo, sem dependência do Homebrew.

## Comportamento seguro

O modo atual é **Copy / Update**: copia arquivos novos ou alterados sem apagar
arquivos extras do destino.

A verificação pode usar comparação rápida ou MD5 quando suportado. Arquivos
sem checksum disponível podem usar comparação por tamanho.

## Limitações conhecidas

- Compatível somente com Macs Apple Silicon e macOS 14.6 ou mais recente.
- O aplicativo ainda não possui assinatura Developer ID nem notarização Apple.
- O macOS pode exigir **Open Anyway** na primeira abertura.
- Enquanto o OAuth estiver em modo Testing, a conta Google precisa estar
  cadastrada como testadora e poderá exigir nova conexão depois de sete dias.
- Esta ainda é uma versão de avaliação. Não use a beta como única cópia de
  arquivos importantes.

Antes do primeiro teste, consulte o [Guia rápido](GUIA-RAPIDO.md).
