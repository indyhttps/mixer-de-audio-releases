# Mixer de Áudio ASIO — Windows 11

[**BAIXAR O INSTALADOR**](https://github.com/indyhttps/mixer-de-audio-releases/releases/latest/download/instalador-mixer-asio.zip)

Mixer de voz com ajustes de altura, timbre, gate de ruído e presets. O processamento inicia automaticamente depois que a Focusrite e a entrada física estão configuradas. A versão 1.3.21 inclui calibração do gate e diagnóstico ASIO local.

## Instalar e usar

1. Baixe o ZIP acima e escolha **Extrair Tudo** no Windows.
2. Abra **`02 - Instalar ou reparar.bat`** na pasta extraída.
3. Use o atalho **Mixer de Áudio ASIO** na Área de Trabalho ou **`01 - Abrir.bat`**.
4. Selecione no Mixer a entrada física em que o microfone está conectado.
5. No Discord, Zoom ou gravador, escolha a entrada **Focusrite — Loopback L + R** para receber a voz processada. Mantenha o Mixer aberto enquanto usa os efeitos.

| Ação | Arquivo |
|---|---|
| Abrir | `01 - Abrir.bat` |
| Instalar, atualizar ou reparar | `02 - Instalar ou reparar.bat` |
| Desinstalar, após confirmação | `03 - Desinstalar.bat` |

Esses três comandos também ficam na pasta instalada: `%LOCALAPPDATA%\Programs\Mixer de Áudio ASIO\`. Guarde a pasta extraída completa para poder reparar a instalação. A desinstalação preserva seus presets, preferências, o driver Focusrite e o Focusrite Control 2.

## Preparar a Focusrite

Esta edição usa a **Focusrite Scarlett 2i2 de 4ª geração**, com driver oficial e Focusrite Control 2, instalados separadamente. Outros modelos não foram validados. [Downloads oficiais da Focusrite](https://downloads.focusrite.com/focusrite/scarlett-4th-gen/scarlett-2i2-4th-gen).

- Mantenha a entrada de captura **Loopback L + R** ativa no Windows.
- Desative a saída WDM de reprodução da Focusrite para reservar Playback 1–2 ao ASIO. Use outro dispositivo como saída normal do Windows.
- No Focusrite Control 2, mantenha **Direct Monitor → Loopback desligado**. Evite que outro aplicativo ASIO envie áudio para Playback 1–2, pois esse áudio também pode chegar ao Loopback.
- O Mixer acompanha a taxa de amostragem e o buffer configurados no driver. **48 kHz e 192 amostras são uma configuração validada, não um requisito fixo.** Ajuste esses valores pelos controles oficiais da Focusrite; o aplicativo informa quando a configuração ou a preparação da rota impede o processamento.

## Gate, calibração e diagnóstico

O limiar do **Gate de ruído** controla quanto ruído é silenciado entre as frases. O gate permanece aberto por 300 ms após o sinal cair abaixo do limiar, sem acrescentar atraso ao áudio.

**Calibrar** mede 3 segundos de silêncio e 5 segundos de fala para ajustar apenas o limiar do gate do microfone selecionado. Ganho, taxa, buffer e controles da Focusrite permanecem sob seu controle.

**Diagnóstico ASIO** apresenta o estado atual localmente. Ele não envia informações a um servidor nem executa reparos dos componentes da edição legada.

## Compatibilidade

- **Windows 11 em Intel/AMD x64 ou ARM64.** O .NET e o Windows App SDK necessários estão incluídos no pacote. A instalação e a janela podem abrir sem uma interface de áudio conectada; o processamento depende da preparação descrita acima.
- Em ARM64, o app usa a emulação x64 do Windows 11 e precisa do driver Focusrite oficial compatível com ARM. A arquitetura dos binários foi conferida, mas **o áudio do Mixer ainda não foi testado em hardware ARM64**. [Compatibilidade ARM da Focusrite](https://support.focusrite.com/hc/en-gb/articles/21643588192146-Focusrite-compatibility-with-Windows-on-Arm).
- Os executáveis próprios da versão **1.3.21 não têm assinatura Authenticode**. Smart App Control e outras políticas de execução podem bloquear o aplicativo. A assinatura RSA do ZIP não substitui a assinatura dos executáveis nem garante sua aceitação pelo Windows. O pacote não instala certificados nem altera as proteções do sistema. [Requisitos de assinatura da Microsoft](https://learn.microsoft.com/en-us/windows/apps/develop/smart-app-control/code-signing-for-smart-app-control).

## Atualizar ou reparar

Baixe o pacote mais recente, extraia-o por completo e execute **`02 - Instalar ou reparar.bat`**. As preferências são mantidas. Esse processo também atualiza a versão exibida pelo Windows e repõe arquivos próprios ausentes ou corrompidos.

A edição ASIO usa **atualização manual pelo pacote**. O atualizador automático e os pacotes chamados `instalador-mixer-de-audio.zip` pertencem à edição legada.

## Arquivos da release

Na [página da versão](https://github.com/indyhttps/mixer-de-audio-releases/releases/latest), o **ZIP** é o instalador completo. O arquivo `.sha256` permite conferir o hash do download; `.sig` contém a assinatura RSA do ZIP, verificável com a chave pública de releases. Esses arquivos auxiliares não são instaladores. O manifesto interno verifica os arquivos antes da instalação, mas sozinho não comprova a origem.

Qualquer pessoa pode baixar e usar gratuitamente o aplicativo em computadores compatíveis, conforme `Programa/TERMOS-DE-USO.txt`. As licenças dos componentes estão em `Programa/LICENCAS/`. Este repositório hospeda os downloads e as instruções; o código-fonte é mantido em repositório privado.
