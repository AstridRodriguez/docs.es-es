---
title: Ejecutar aplicaciones basadas en microservicios y compuestas en entornos de producción
description: Conozca los componentes clave para ejecutar aplicaciones basadas en contenedores en producción
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: bd8b84f788ce013dfe25199dac34e3c59aa35284
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220970"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ejecutar aplicaciones basadas en microservicios y compuestas en entornos de producción

Aplicaciones compuestas por varios microservicios deben implementarse en clústeres de orchestrator con el fin de simplificar la complejidad de implementación y hacerla viable desde un punto de vista de TI. Sin un clúster de orchestrator, sería muy difícil de implementar y escalar horizontalmente una aplicación de microservicios complejos.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introducción a los clústeres de contenedor, los programadores y orquestadores

Anteriormente en este libro electrónico, introdujimos *clústeres* y *programadores* como parte de la discusión de arquitectura de software y de desarrollo. Ejemplos de clústeres de Docker son Docker Swarm y Mesosphere Datacenter Operating System (DC/OS). Ambos se pueden ejecutar como parte de la infraestructura proporcionada por Microsoft Azure Container Service.

Cuando las aplicaciones están escaladas horizontalmente en varios sistemas de host, la capacidad de administrar cada sistema host y abstraer la complejidad de la plataforma subyacente se convierte en atractiva. Eso es precisamente lo que proporcionan los orquestadores y los programadores. Echemos un vistazo a ellos aquí:

- **Programadores**. "Programación" hace referencia a la capacidad para que un administrador cargar un archivo de servicio en un sistema host que establece cómo ejecutar un contenedor específico. Iniciando contenedores en un clúster de Docker suele conocerse como la programación. Aunque la programación se refiere a la ley específica de la carga de la definición de servicio, en un sentido más general, los programadores son responsables de enlace en el sistema de inicio de un host para administrar servicios en cualquier capacidad necesaria.

   Un programador de clúster tiene varios objetivos: usar de forma eficaz los recursos del clúster, trabajar con restricciones de selección de ubicación proporcionada por el usuario, la programación de aplicaciones rápidamente a no dejarlos en un estado pendiente, tener un grado de "imparcialidad", que se va a sólida a errores, y siempre estarán disponibles.

- **Orquestación**. Plataformas amplían las capacidades de administración de ciclo de vida a cargas de trabajo complejas y de varios contenedores, implementadas en un clúster de hosts. Mediante la abstracción de la infraestructura del host, las herramientas de orquestación dar a los usuarios una manera de tratar todo el clúster como un destino de implementación único.

   El proceso de orquestación implica las herramientas y una plataforma que puede automatizar todos los aspectos de administración de aplicaciones desde la ubicación inicial o la implementación por contenedor; mover contenedores a hosts diferentes dependiendo de su host estado o rendimiento; actualizaciones y las funciones que admiten el escalado y la conmutación por error; la supervisión de estado de control de versiones y gradual y mucho más.

   Orquestación es un término amplio que hace referencia al contenedor de programación, administración del clúster y, posiblemente, el aprovisionamiento de hosts adicionales.

Las funcionalidades proporcionadas por los orquestadores y los programadores son muy complejas para desarrollar y crear desde cero y, por lo tanto, normalmente querrá hacer uso de soluciones de orquestación ofrecidos por proveedores.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](manage-production-docker-environments.md)