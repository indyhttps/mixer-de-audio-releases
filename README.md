# Mixer de Áudio ASIO — Windows 11

[**BAIXAR O INSTALADOR**](https://github.com/indyhttps/mixer-de-audio-releases/releases/latest/download/instalador-mixer-asio.zip)

Mixer de voz com ajustes de altura, timbre e presets. O Loopback inicia automaticamente depois que a Focusrite e a entrada física estão configuradas.

## Instalar e usar

1. Baixe o ZIP acima e escolha **Extrair Tudo** no Windows.
2. Abra **`02 - Instalar ou reparar.bat`** na pasta extraída.
3. Use o atalho **Mixer de Áudio ASIO** na Área de Trabalho ou **`01 - Abrir.bat`**.
4. No Discord, Zoom ou gravador, escolha a entrada **Focusrite — Loopback L + R**.

| Ação | Arquivo |
|---|---|
| Abrir | `01 - Abrir.bat` |
| Instalar, atualizar ou reparar | `02 - Instalar ou reparar.bat` |
| Desinstalar, após confirmação | `03 - Desinstalar.bat` |

Esses três comandos também ficam na pasta instalada: `%LOCALAPPDATA%\Programs\Mixer de Áudio ASIO\`.
Guarde a pasta extraída completa para poder reparar a instalação. A desinstalação preserva seus presets, preferências, o driver Focusrite e o Focusrite Control 2.

## Compatibilidade

- **Windows 11, em processadores Intel/AMD x64 ou ARM64.** O .NET e o Windows App SDK necessários já estão incluídos. Em ARM64, o app usa a emulação x64 do próprio Windows; instale a versão oficial atual do driver Focusrite para ARM. A compatibilidade dos binários foi conferida, mas o áudio ainda não foi testado em hardware ARM.
- A instalação e a janela podem abrir sem uma interface de áudio conectada. Para processar a voz, esta edição exige **Focusrite Scarlett 2i2 de 4ª geração**, com driver oficial e Focusrite Control 2. [Downloads oficiais da Focusrite](https://downloads.focusrite.com/focusrite/scarlett-4th-gen/scarlett-2i2-4th-gen).
- Configure a Focusrite em **48 kHz, buffer 192**, selecione a entrada física no Mixer e mantenha o Loopback de captura ativo. A saída WDM de reprodução da Focusrite deve estar desativada para reservar Playback 1–2 ao ASIO; use outro dispositivo como saída normal do Windows. O aplicativo informa quando essa preparação ainda falta.
- O certificado atual do aplicativo é local. PCs que exigem um publicador reconhecido pelo Smart App Control podem bloquear a execução. Esta release não instala certificados nem altera as proteções do Windows. [Requisitos de assinatura da Microsoft](https://learn.microsoft.com/en-us/windows/apps/develop/smart-app-control/code-signing-for-smart-app-control).

## Atualizar

Baixe o pacote mais recente e execute **`02 - Instalar ou reparar.bat`**. As preferências são mantidas. A edição ASIO usa esse fluxo de atualização; o atualizador automático e os pacotes chamados `instalador-mixer-de-audio.zip` pertencem à edição legada.

## Arquivos da release

Na [página da versão](https://github.com/indyhttps/mixer-de-audio-releases/releases/latest), o **ZIP** é o instalador completo. Os arquivos `.sha256` e `.sig` permitem conferir a integridade e a assinatura do download; não são instaladores. O manifesto interno verifica os arquivos antes da instalação, mas sozinho não comprova a origem.

Qualquer pessoa pode baixar e usar gratuitamente o aplicativo em computadores compatíveis, conforme `Programa/TERMOS-DE-USO.txt`. As licenças dos componentes estão em `Programa/LICENCAS/`. Este repositório hospeda os downloads e as instruções; o código-fonte é mantido em repositório privado.
