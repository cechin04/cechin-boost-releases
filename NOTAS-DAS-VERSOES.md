# Notas das versões

Versões publicadas neste repositório, da mais nova para a mais antiga. Cada página de versão traz também os SHA-256 e a identificação da compilação.

## 0.12.0

- **FPS de jogos Vulkan, OpenGL e com DXVK** no HUD e no histórico. Antes, só jogos DirectX eram medidos. A API aparece junto do número (por exemplo "Vulkan (DXVK 3.1.1)").
- **Correção do FPS ao vivo no HUD**: desde a 0.4, ele podia aparecer muito maior que o real (cerca de 12 vezes). As médias e o 1% low do histórico estavam certos. Agora o HUD acompanha o jogo e some quando ele para de desenhar.
- **Experiências com bibliotecas (DXVK) mais seguras**:
  - a placa de vídeo é conferida contra o que o DXVK 3.1.1 pede (Vulkan 1.3, extensões e recursos), não só se o Vulkan está instalado;
  - "preparado" (arquivos na pasta) e "confirmado em uso" (o jogo carregou o DXVK) aparecem separados;
  - desfazer só apaga o que é da experiência e deixa intacto o que já existia, inclusive o cache de outros jogos.
- **Atualizações**: o app procura versão nova sozinho ao abrir e a cada 6 horas (dá para desligar), mostra as notas e o progresso do download e instala só quando você clica. Antes de instalar, fecha do jeito normal: ventoinhas de volta ao automático, Modo Jogo e medição encerrados. Se não conseguir confirmar isso, adia e mostra o motivo. Nunca instala com jogo aberto.

**Limitações conhecidas**

- O FPS conta os quadros que o jogo entregou ao Windows, não os que apareceram na tela. Os números ao vivo atrasam até cerca de 1 segundo.
- Jogos Vulkan e OpenGL: a API é deduzida das bibliotecas que o jogo carregou.
- DXVK: nenhum dos jogos do PC de desenvolvimento pode recebê-lo (anticheat ou DirectX 12). Ele foi conferido só numa carga de teste, em que ficou mais lento que o DirectX nativo.
- O executável não tem assinatura de código: o Windows pode mostrar o aviso do SmartScreen na primeira vez. Os arquivos e o atualizador são conferidos pelo SHA-256 e pela assinatura de atualização.
- A versão portátil não se instala sozinha: ela avisa da versão nova e abre a página para baixar o ZIP, que é extraído por cima da pasta atual (a pasta `data` fica).
