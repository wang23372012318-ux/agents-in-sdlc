---
title: "Lección 12 - Publicar el sitio con GitHub Pages"
description: "Usa la aplicación GitHub Copilot para configurar un flujo de trabajo de Pages, revisar su solicitud de incorporación de cambios y comprobar el Space Quiz publicado."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publica Space Quiz en GitHub Pages para que todo el mundo pueda acceder a él. Copilot puede preparar el flujo de trabajo y guiarte durante la publicación, pero debes revisar los cambios y confirmar que el sitio está disponible.

En esta lección:

- Pide a Copilot que configure una publicación en GitHub Pages.
- Revisa el flujo de trabajo y la solicitud de incorporación de cambios antes de combinarla.
- Sigue la publicación y comprueba el sitio publicado.

## Escenario

Space Quiz ya está en un repositorio de GitHub, pero las personas necesitan una forma sencilla de probarlo. Publicar el sitio de un solo archivo con GitHub Pages permite acceder a él mediante una URL pública sin añadir un servidor ni una dependencia del entorno de ejecución.

## Pide a Copilot que prepare la publicación

> [!WARNING]
> Crear una solicitud de incorporación de cambios puede confirmar y enviar código. Revisa la configuración de aprobación y el repositorio de destino antes de enviar este mensaje. Si seleccionas **Approve all**, no des por hecho que se mostrará otra solicitud de confirmación.

En la sesión de la aplicación Copilot para `space-quiz`, envía este mensaje:

```plaintext
Prepara la publicación de GitHub Pages para este repositorio. Crea un flujo de trabajo de GitHub Actions que, si es necesario, compile el sitio web y lo publique en GitHub Pages cuando los cambios lleguen a la rama predeterminada. Añade un README que describa la aplicación y cómo ejecutarla localmente si aún no existe. Crea una solicitud de incorporación de cambios con estos cambios e indica el enlace y los ajustes o permisos de Pages necesarios. No combines la solicitud, no habilites la combinación automática, no cambies la configuración de Pages ni publiques el sitio. Detente y espera a que revise los cambios.
```

## Revisa el flujo de trabajo y la solicitud de incorporación de cambios

1. Confirma que el README solo se añade si el repositorio aún no tiene uno.
2. Revisa los cambios de la solicitud, incluidos los pasos de compilación y publicación del flujo de trabajo, los desencadenadores y los permisos.
3. Confirma que el flujo de trabajo publica desde la rama predeterminada, no desde una solicitud de incorporación de cambios sin combinar.
4. Solicita las correcciones necesarias y revisa el diff actualizado. Espera a que se superen las comprobaciones obligatorias de la solicitud antes de autorizar la combinación.

## Autoriza la combinación y la publicación

> [!WARNING]
> El siguiente mensaje autoriza al agente a combinar la solicitud revisada, cambiar la configuración de Pages del repositorio y publicar el sitio. Envíalo solo después de revisar los cambios y confirmar el repositorio y la solicitud. Según la configuración de aprobación, estas acciones podrían realizarse sin otra solicitud de confirmación.

Sustituye `<PR_NUMBER>` por el número de la solicitud que has revisado y envía este mensaje por separado:

```plaintext
He revisado la solicitud de incorporación de cambios <PR_NUMBER> de este repositorio y autorizo su combinación y publicación. Habilita GitHub Pages con GitHub Actions, combina esa solicitud solo después de que se superen las comprobaciones obligatorias y supervisa la publicación hasta que se complete correctamente. Indica la URL final del sitio web publicado. Si no tienes permiso para habilitar Pages o combinar la solicitud, dime exactamente qué debo aprobar o hacer; no informes de que la publicación se ha completado hasta que el sitio esté disponible.
```

![Diagrama de tres etapas: una solicitud de incorporación de cambios de space-quiz combinada; una ejecución correcta de GitHub Actions Deploy website con los pasos Build website, Upload artifact y Deploy to Pages; y Space Quiz publicado en yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Comprueba la publicación

1. Sigue la ejecución de publicación de GitHub Actions hasta que se complete correctamente.
2. Abre la URL indicada y confirma que se carga Space Quiz.

Si el agente no puede habilitar Pages o combinar la solicitud, sigue las instrucciones concretas que te proporcione. No des la tarea por terminada hasta que la publicación se complete y el sitio esté disponible.

## Resumen y siguientes pasos

Space Quiz ya está disponible como sitio web y has comprobado la publicación en lugar de confiar únicamente en el informe del agente. Continúa con la [Lección 13: Repaso y próximos pasos][next-lesson].

[next-lesson]: ../13-review/
