# MCSyncDrive - Política de Privacidade

[English](../PRIVACY.md) · [Português](PRIVACY.md)

Última atualização: 30 de julho de 2026

Versão do documento: `mcsyncdrive-privacy-2026-07-30`

Esta Política de Privacidade descreve como o MCSyncDrive ("MCSyncDrive", "o
aplicativo", "nós") trata as informações quando você utiliza o aplicativo no
seu Mac. O aplicativo é desenvolvido e mantido por Magno Ciqueira sob a
plataforma Nexus, e o tratamento é realizado de acordo com a Lei Geral de
Proteção de Dados brasileira (LGPD — Lei nº 13.709/2018) e, quando aplicável,
com outras leis de proteção de dados.

Ao instalar ou usar o MCSyncDrive, você reconhece ter acesso a esta política.

## 1. Identificação do Controlador

O MCSyncDrive é desenvolvido e mantido por Magno Ciqueira, responsável pelo
tratamento dos dados pessoais descritos nesta política.

Contato para assuntos de privacidade: [sync@mcnexus.app](mailto:sync@mcnexus.app)

## 2. O que o MCSyncDrive faz

O MCSyncDrive é um aplicativo nativo para macOS que conecta sua conta do Google
Drive e transfere arquivos entre o Google Drive e dispositivos de
armazenamento locais (SSDs ou outros volumes). Todas as operações de
transferência são executadas localmente no seu Mac por meio do rclone, uma
ferramenta de linha de comando incorporada ao aplicativo. Nenhum arquivo,
prévia ou metadado é enviado para servidores operados por Magno Ciqueira ou
pela plataforma Nexus.

## 3. Informações coletadas e como são utilizadas

### 3.1 Conta Google e acesso ao Drive

O MCSyncDrive conecta sua conta Google usando OAuth 2.0. Dependendo do escopo
de acesso escolhido, o aplicativo poderá solicitar:

- **`drive`** — acesso de leitura e gravação aos arquivos que sua conta pode
  acessar no Google Drive, Meu Drive, Compartilhados comigo e Drives
  compartilhados; ou
- **`drive.readonly`** — acesso somente de leitura e download, sem a
  possibilidade de enviar ou modificar arquivos.

O aplicativo utiliza o escopo que você selecionou explicitamente. É possível
alterar o escopo reconectando sua conta pelo próprio aplicativo.

Seu nome e endereço de e-mail podem ser exibidos no aplicativo para confirmar
qual conta está conectada. Essas informações são lidas do seu perfil Google e
nunca são transmitidas para nenhum servidor além dos do Google.

### 3.2 Tokens OAuth

Os tokens de autenticação emitidos pelo Google são armazenados exclusivamente
no arquivo de configuração do rclone, localizado em:

```
~/Library/Application Support/MCSyncDrive/rclone.conf
```

Este arquivo é criptografado pelo rclone. A chave de criptografia é gerada
aleatoriamente para o seu Mac, protegida com AES-GCM e armazenada em:

```
~/Library/Application Support/MCSyncDrive/Security/rclone-secret.v1
```

Os tokens jamais são registrados em logs, incluídos em relatórios de operação
ou transmitidos para qualquer servidor operado por Magno Ciqueira ou pela
plataforma Nexus. As permissões do arquivo de configuração são definidas como
`0600` (somente leitura e gravação pelo proprietário).

### 3.3 Operações com arquivos locais

O MCSyncDrive lê e grava arquivos nos volumes de armazenamento e nas pastas do
Google Drive que você selecionar. O aplicativo:

- acessa apenas as pastas de origem e destino que você escolhe explicitamente
  para cada operação;
- não lê, copia ou transmite seus arquivos para nenhum servidor além do
  endpoint do Google Drive que você configurar;
- não faz varredura em pastas que você não selecionou;
- não indexa nem armazena em cache o conteúdo dos arquivos além do necessário
  para a transferência e a verificação realizadas pelo rclone.

### 3.4 Histórico de operações e logs

O MCSyncDrive mantém um histórico local de operações que registra:

- nome do projeto e tipo de operação;
- direção da transferência, caminhos de origem e destino;
- identificadores de volume para SSDs externos (caminho e UUID, quando
  disponíveis);
- horários de início e término de cada operação;
- quantidade de arquivos e pastas, tamanho total, bytes transferidos,
  velocidade média e duração;
- modo de transferência, tipo de verificação e filtros aplicados;
- código de saída do rclone e resumo de arquivos ausentes, diferentes ou com
  erro;
- o nome do usuário que confirmou uma operação de limpeza.

Esse histórico é armazenado localmente em:

```
~/Library/Application Support/MCSyncDrive/
```

Os logs de operação são armazenados em:

```
~/Library/Logs/MCSyncDrive/
```

Nenhum desses dados é enviado para qualquer servidor remoto. O histórico é
mantido localmente até você limpá-lo pelo aplicativo ou desinstalar o
aplicativo.

### 3.5 Sem analytics ou telemetria

O MCSyncDrive não inclui bibliotecas de analytics, relatórios de falhas,
agentes de telemetria ou SDKs de publicidade. Nenhum dado de uso é coletado ou
transmitido automaticamente.

## 4. API do Google Drive e minimização de dados

O aplicativo acessa o Google Drive exclusivamente por meio da API do Google
Drive, utilizando as credenciais da sua própria conta Google. São solicitados
apenas os dados necessários para listar, transferir e verificar os arquivos que
você seleciona. O MCSyncDrive não lê Gmail, Google Agenda, Google Contatos nem
qualquer outro serviço do Google.

O aplicativo não compartilha, vende nem utiliza seus dados do Google Drive para
nenhuma finalidade além das operações de transferência de arquivos que você
inicia.

## 5. Uso do rclone

O MCSyncDrive incorpora o rclone ([rclone.org](https://rclone.org)) para
realizar transferências e verificações de arquivos. O rclone se comunica
diretamente com o Google Drive em seu nome, utilizando seu token OAuth. O
processo do rclone é executado localmente no seu Mac e não retransmite dados
por meio de nenhum servidor intermediário operado por Magno Ciqueira ou pela
plataforma Nexus.

Os avisos de terceiros referentes ao rclone e suas dependências estão incluídos
dentro do pacote do aplicativo em `ThirdPartyNotices.txt`.

## 6. Permissões solicitadas

| Permissão | Motivo |
|---|---|
| Google Drive (leitura e gravação ou somente leitura) | Realizar as transferências e verificações de arquivos que você inicia |
| Acesso a pastas locais (seletor do Finder) | Ler ou gravar nos volumes SSD locais que você selecionar |
| Acesso à rede | Conectar à API do Google Drive em seu nome |

O MCSyncDrive não solicita acesso a contatos, microfone, câmera, localização ou
qualquer outro recurso do sistema além dos listados acima.

## 7. Dados armazenados no seu Mac

Todos os dados do aplicativo permanecem no seu Mac:

| Local | Conteúdo |
|---|---|
| `~/Library/Application Support/MCSyncDrive/` | Configuração do rclone (criptografada), histórico de operações, dados do projeto, manifestos |
| `~/Library/Logs/MCSyncDrive/` | Logs de operações e transferências |
| `~/Library/Caches/MCSyncDrive/` | Listagens remotas temporárias (reconstituíveis, podem ser removidas pelo macOS) |

A desinstalação do aplicativo não remove esses diretórios automaticamente.
Você pode excluí-los manualmente se desejar remover todos os dados locais.

## 8. Compartilhamento de dados

O MCSyncDrive não compartilha seus dados com nenhum terceiro, exceto:

- **Google LLC:** seus arquivos e credenciais são transmitidos ao Google Drive
  por meio da API do Google Drive como parte das operações de transferência que
  você inicia. A própria
  [Política de Privacidade](https://policies.google.com/privacy?hl=pt-BR) do
  Google e a
  [Política de Dados do Usuário dos Serviços de API](https://developers.google.com/terms/api-services-user-data-policy)
  se aplicam aos dados processados pelo Google.

Nenhum outro dado é compartilhado com qualquer parte. O MCSyncDrive não vende
nem aluga dados.

## 9. Segurança

O MCSyncDrive aplica as seguintes medidas para proteger seus dados:

- tokens OAuth armazenados em um arquivo de configuração criptografado pelo
  rclone, com permissão `0600`;
- chave de criptografia protegida com AES-GCM e vinculada ao seu Mac;
- nenhum token registrado em logs de operação ou no histórico;
- caminhos de arquivos passados como argumentos de processo, sem concatenação
  de comandos de shell;
- comunicação de rede com a API do Google Drive realizada exclusivamente via
  HTTPS.

## 10. Crianças e menores

O MCSyncDrive é um aplicativo profissional destinado a fluxos de trabalho de
pós-produção audiovisual e não é direcionado a pessoas com menos de 18 anos.
Não coletamos intencionalmente dados de crianças ou menores.

## 11. Direitos do titular dos dados

Nos termos da legislação aplicável, você pode solicitar:

- confirmação de que o tratamento ocorre;
- acesso aos dados mantidos sobre você;
- correção de dados imprecisos ou desatualizados;
- exclusão de dados, respeitadas as obrigações legais e operacionais.

Como o MCSyncDrive armazena todos os dados localmente no seu Mac, você pode
inspecionar, exportar ou excluir seus dados a qualquer momento acessando os
diretórios listados na Seção 7. Para exercer direitos relacionados a dados
tratados por Magno Ciqueira fora do aplicativo, entre em contato pelo endereço:

[sync@mcnexus.app](mailto:sync@mcnexus.app)

## 12. Usuários internacionais e transferências

O MCSyncDrive é operado no Brasil. Buscamos cumprir os requisitos de proteção
de dados aplicáveis a cada relação, incluindo, quando relevante, o RGPD para
residentes no Espaço Económico Europeu e no Reino Unido, e as leis de
privacidade aplicáveis a residentes na Califórnia.

Como todos os dados do aplicativo são armazenados localmente no seu próprio
dispositivo e transmitidos somente aos servidores do Google sob sua própria
conta, nenhum dado pessoal é transferido para servidores operados por Magno
Ciqueira fora do Brasil.

## 13. Alterações

Esta política poderá ser atualizada para refletir mudanças no aplicativo, em
requisitos legais ou nos serviços integrados. A data da última revisão constará
no início do documento. Mudanças materiais poderão ser comunicadas pelo
repositório do aplicativo ou pelo canal de suporte indicado abaixo.

## 14. Contato

- Privacidade: [sync@mcnexus.app](mailto:sync@mcnexus.app)
- Suporte técnico: [github.com/ciqueira/MCSync/issues](https://github.com/ciqueira/MCSync/issues)
