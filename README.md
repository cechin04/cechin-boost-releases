# CECHIN BOOST

Otimizador de Windows para jogos, gratuito e em português. Diagnostica o PC, mostra o que vale a pena ajustar no seu hardware e guarda um backup de cada mudança para desfazer depois.

Este repositório só distribui o programa: instaladores, versão portátil, notas das versões e arquivos de verificação. O código-fonte não é público.

## Baixar

Abra a [versão mais recente](../../releases/latest) e escolha um dos arquivos:

| Arquivo | Para quê |
|---|---|
| `CechinBoost-Setup-<versão>.exe` | Instalador para Windows 10 e 11 (64 bits). Instala para todos os usuários e pede administrador. |
| `CechinBoost-Portable-<versão>.zip` | Versão portátil: roda sem instalar, com os dados numa pasta ao lado do programa. |
| `SHA256SUMS.txt` | Os códigos SHA-256 de cada arquivo, para conferir o download. |
| `latest.json` e `.sig` | Usados pelo atualizador do próprio programa. Você não precisa abrir. |
| `AVISOS-DE-TERCEIROS.txt` | Licenças dos componentes de código aberto usados dentro do programa. |

## Instalar

**Instalador**
1. Baixe `CechinBoost-Setup-<versão>.exe` e abra.
2. O programa ainda não tem assinatura de código. Por isso o Windows pode mostrar "O Windows protegeu o computador". Nesse caso, clique em **Mais informações** e depois em **Executar assim mesmo**, só se o SHA-256 conferir (veja abaixo).
3. O CECHIN BOOST abre como administrador. Ele precisa disso para ler sensores e aplicar ajustes do Windows.

**Portátil**
1. Baixe `CechinBoost-Portable-<versão>.zip` e extraia a pasta `CechinBoost-Portable` onde quiser (de preferência numa pasta só sua).
2. Abra `CechinBoost.exe`. Configurações, histórico e backups ficam na pasta `data`, ao lado dele.

## Conferir o download

No PowerShell, na pasta do download:

```powershell
Get-FileHash .\CechinBoost-Setup-<versão>.exe -Algorithm SHA256
```

O código precisa ser igual ao da linha desse arquivo em `SHA256SUMS.txt`.

## Atualizar

- **Instalado:** o programa procura versão nova sozinho, ao abrir e a cada 6 horas. Ele só lê a página de versões deste repositório e dá para desligar a procura em Configurações > Atualizações. Quando há versão nova, ele mostra as notas; ao clicar em instalar, baixa, confere a assinatura e fecha do jeito normal antes de instalar (ventoinhas de volta ao automático, Modo Jogo e medição encerrados). Nunca instala com jogo aberto. Configurações, histórico e backups ficam onde estão.
- **Portátil:** o programa avisa da versão nova e abre esta página. Baixe o ZIP novo e extraia por cima da pasta atual: a pasta `data` continua lá.

## Privacidade

O CECHIN BOOST não envia nada sobre você nem sobre o seu PC. Não tem conta, anúncio nem estatística de uso. Ele usa a internet para o que você pede (testes de rede e instalações pelo winget, direto da fonte oficial) e para procurar versão nova, que só lê a página pública de versões deste repositório.

## Notas das versões

Cada versão traz as mudanças e as limitações conhecidas na própria página da versão. O histórico fica em [NOTAS-DAS-VERSOES.md](NOTAS-DAS-VERSOES.md).

## Licença

© 2026 Cechin. O CECHIN BOOST é distribuído gratuitamente nestes pacotes; o código próprio dele não é de código aberto. Os componentes de terceiros usados dentro do programa seguem as próprias licenças, listadas em [AVISOS-DE-TERCEIROS.txt](AVISOS-DE-TERCEIROS.txt) e em cada versão.
