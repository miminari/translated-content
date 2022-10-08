---
title: Lista de valores padrões de Accept
slug: Web/HTTP/Content_negotiation/List_of_default_Accept_values
tags:
  - Accept
  - HTTP
  - Negociação de conteúdo
  - Referencia
translation_of: Web/HTTP/Content_negotiation/List_of_default_Accept_values
---
{{HTTPSidebar}}

Este artigo documenta os valores padrão para o cabeçalho HTTP [`Accept`](/en-US/docs/Web/HTTP/Headers/Accept) para entradas e versões específicas do navegador.

## Valores padrão

Estes são os valores enviados quando o contexto não fornece mais informações. Observe que todos os navegadores adicionam o tipo MIME `*/*` para cobrir todos os casos. Isso é normalmente usado para solicitações iniciadas por meio da barra de endereços de um navegador ou por meio de um elemento HTML {{HTMLElement("a")}}.

| User Agent          | Valor                                                                                                                                                                                                                                                         | Comentário                                                                                                                                                                                                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firefox             | `text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8` (desde o Firefox 66) `text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8` (no Firefox 65) `text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8` (antes) | No Firefox 65 e versões anteriores, esse valor pode ser modificado usando o parâmetro [`network.http.accept.default`](http://kb.mozillazine.org/Network.http.accept.default). ([fonte](https://hg.mozilla.org/mozilla-central/file/tip/modules/libpref/init/all.js#l1750)) |
| Safari, Chrome      | `text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8`                                                                                                                                                                       | ([fonte](/pt-BR/docs/))                                                                                                                                                                                                                                                    |
| Safari 5            | `text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8`                                                                                                                                                                                             | Esta é uma melhoria em comparação com os cabeçalhos `Accept` já que não mais classifica `image/png` acima de `text/html`                                                                                                                                                   |
| Internet Explorer 8 | `image/jpeg, application/x-ms-application, image/gif, application/xaml+xml, image/pjpeg, application/x-ms-xbap, application/x-shockwave-flash, application/msword, */*`                                                                                       | Veja [IE and the Accept Header (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/ieinternals/archive/2009/07/01/ie-and-the-accept-header.aspx).                                                                                                                       |
| Edge                | `text/html, application/xhtml+xml, image/jxr, */*`                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                            |
| Opera               | `text/html, application/xml;q=0.9, application/xhtml+xml, image/png, image/webp, image/jpeg, image/gif, image/x-xbitmap, */*;q=0.1`                                                                                                                           |                                                                                                                                                                                                                                                                            |

## Valores para uma imagem

Ao solicitar uma imagem, como por meio de um elemento HTML {{HTMLElement("img")}}, user-agent geralmente define uma lista específica de tipos de mídia para ser recebida.

| User Agent                      | Valor                                                                                                        | Comentário                                                                                                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firefox                         | `image/webp,*/*` (desde o Firefox 65) `*/*` (desde o Firefox 47) `image/png,image/*;q=0.8,*/*;q=0.5` (antes) | Esse valor pode ser modificado usando o parâmetro `image.http.accept`. [fonte](https://hg.mozilla.org/mozilla-central/file/tip/modules/libpref/init/all.js#l4735)                   |
| Safari                          | `*/*`                                                                                                        |                                                                                                                                                                                     |
| Chrome                          | `image/webp,image/apng,image/*,*/*;q=0.8`                                                                    | [fonte](https://chromium.googlesource.com/chromium/src.git/+/master/content/renderer/loader/web_url_loader_impl.cc#99)                                                              |
| Internet Explorer 8 ou anterior | `*/*`                                                                                                        | Veja [IE and the Accept Header (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/ieinternals/archive/2009/07/01/ie-and-the-accept-header.aspx)                                 |
| Internet Explorer 9             | `image/png,image/svg+xml,image/*;q=0.8, */*;q=0.5`                                                           | Veja [Fiddler is better with Internet Explorer 9 (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/fiddler/archive/2011/02/10/fiddler-is-better-with-internet-explorer-9.aspx) |

## Valores para um vídeo

Quando um vídeo é solicitado, via o elemento HTML {{HTMLElement("video")}}, a maioria dos navegadores usam valores específicos.

| User Agent                      | Valor                                                                              | Comentário                                                                                                                                                         |
| ------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Firefox anterior a 3.6          | _sem suporte a {{HTMLElement("video")}}_                                   |                                                                                                                                                                    |
| Firefox 3.6 e posterior         | `video/webm,video/ogg,video/*;q=0.9,application/ogg;q=0.7,audio/*;q=0.6,*/*;q=0.5` | veja [bug 489071](https://bugzilla.mozilla.org/show_bug.cgi?id=489071) [fonte](https://hg.mozilla.org/mozilla-central/file/tip/dom/html/HTMLVideoElement.cpp#l136) |
| Chrome                          | `*/*`                                                                              | [fonte](https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#27)                                                            |
| Internet Explorer 8 ou anterior | _sem suporte a {{HTMLElement("video")}}_                                   |                                                                                                                                                                    |

## Valores para recursos de áudio

Quando um arquivo de áudio é solicitado, como via o elemento HTML {{HTMLElement("audio")}}, a maioria dos navegadores usam valores específicos.

| User Agent                      | Value                                                                                        | Comment                                                                                                                                                           |
| ------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firefox 3.6 e posterior         | `audio/webm,audio/ogg,audio/wav,audio/*;q=0.9,application/ogg;q=0.7,video/*;q=0.6,*/*;q=0.5` | Veja [bug 489071](https://bugzilla.mozilla.org/show_bug.cgi?id=489071) [fonte](https://hg.mozilla.org/mozilla-central/file/tip/dom/html/HTMLAudioElement.cpp#l81) |
| Safari, Chrome                  | `*/*`                                                                                        | [fonte](https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#27)                                                           |
| Internet Explorer 8 ou anterior | _sem suporte para {{HTMLElement("audio")}}_                                          |                                                                                                                                                                   |
| Internet Explorer 9             | ?                                                                                            |                                                                                                                                                                   |

## Valores para scripts

Quando um script é solicitado, como via o elemento HTML {{HTMLElement("script")}}, alguns navegadores usam valores específicos.

| User Agent                      | Valor                               | Comentário                                                                                                                                                                          |
| ------------------------------- | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firefox                         | `*/*`                               | Veja [bug 170789](https://bugzilla.mozilla.org/show_bug.cgi?id=170789)                                                                                                              |
| Safari, Chrome                  | `*/*`                               | [fonte](https://chromium.googlesource.com/chromium/src.git/+/master/services/network/loader_util.cc#27)                                                                             |
| Internet Explorer 8 ou anterior | `*/*`                               | Veja [IE and the Accept Header (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/ieinternals/archive/2009/07/01/ie-and-the-accept-header.aspx)                                 |
| Internet Explorer 9             | `application/javascript, */*;q=0.8` | Veja [Fiddler is better with Internet Explorer 9 (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/fiddler/archive/2011/02/10/fiddler-is-better-with-internet-explorer-9.aspx) |

## Valores para uma folha de estilo CSS

Quando uma folha de estilo CSS é solicitada, via o elemento HTML `<link rel="stylesheet">`, a maioria dos navegadores usam valores específicos.

| User Agent                      | Valor                                                                                                                               | Comentário                                                                                                                                                                          |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firefox 4                       | `text/css,*/*;q=0.1`                                                                                                                | Veja [bug 170789](https://bugzilla.mozilla.org/show_bug.cgi?id=170789) [fonte](https://hg.mozilla.org/mozilla-central/file/tip/layout/style/Loader.cpp#l1548)                       |
| Internet Explorer 8 ou anterior | `*/*`                                                                                                                               | Veja [IE and the Accept Header (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/ieinternals/archive/2009/07/01/ie-and-the-accept-header.aspx)                                 |
| Internet Explorer 9             | `text/css`                                                                                                                          | Veja [Fiddler is better with Internet Explorer 9 (blog de MSDN da IEInternals)](http://blogs.msdn.com/b/fiddler/archive/2011/02/10/fiddler-is-better-with-internet-explorer-9.aspx) |
| Safari, Chrome                  | `text/css,*/*;q=0.1`                                                                                                                | [fonte](https://chromium.googlesource.com/chromium/src.git/+/master/content/renderer/loader/web_url_loader_impl.cc#98)                                                              |
| Opera 11.10                     | `text/html, application/xml;q=0.9, application/xhtml+xml, image/png, image/webp, image/jpeg, image/gif, image/x-xbitmap, */*;q=0.1` |                                                                                                                                                                                     |
| Konqueror 4.6                   | `text/css,*/*;q=0.1`                                                                                                                |                                                                                                                                                                                     |