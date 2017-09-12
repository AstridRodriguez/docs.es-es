---
title: "Publicación de la aplicación Hola a todos con Visual Studio 2017"
description: "La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación."
keywords: ".NET, .NET Core, aplicación de consola, publicación, implementación"
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.translationtype: HT
ms.sourcegitcommit: e0271ba3392ce8861dc916714af8c16d4581ce4f
ms.openlocfilehash: 025e132cd5b6a44e98a1270e24ba6b2f9f12812c
ms.contentlocale: es-es
ms.lasthandoff: 08/13/2017

---

# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="cd603-104">Publicación de la aplicación Hola a todos con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cd603-104">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="cd603-105">En [Compilación de una aplicación Hola a todos en C# con .NET Core en Visual Studio 2017](with-visual-studio.md) o [Compilación de una aplicación Hola a todos en Visual Basic con .NET Core en Visual Studio 2017](vb-with-visual-studio.md), ha compilado una aplicación de consola Hola a todos.</span><span class="sxs-lookup"><span data-stu-id="cd603-105">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="cd603-106">En [Depuración de la aplicación Hola a todos en C# con Visual Studio 2017](debugging-with-visual-studio.md), la ha probado con el depurador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd603-106">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="cd603-107">Ahora que está seguro de que funciona como se esperaba, puede publicarla para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="cd603-107">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="cd603-108">Al realizar la publicación, se crea el conjunto de archivos necesarios para ejecutar la aplicación; y puede implementarlos mediante su copia en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="cd603-108">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="cd603-109">Para publicar y ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="cd603-109">To publish and run your application:</span></span> 

1. <span data-ttu-id="cd603-110">Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd603-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="cd603-111">Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="cd603-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="cd603-113">Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="cd603-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="cd603-114">También puede seleccionar **Publicar Hola a todos** en el menú principal **Compilar** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd603-114">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/publish1.png)


   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="cd603-117">Abra una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="cd603-117">Open a console window.</span></span> <span data-ttu-id="cd603-118">Por ejemplo, en el cuadro de texto **Escriba aquí para ejecutar la búsqueda** de la barra de tareas de Windows, escriba `Command Prompt` (o `cmd` para abreviar) y abra una ventana de consola seleccionando la aplicación de escritorio **Símbolo del sistema** o presionando Entrar si está seleccionada en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cd603-118">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="cd603-119">Vaya a la aplicación publicada en el subdirectorio `bin\release\PublishOutput` del directorio del proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd603-119">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="cd603-120">Como se muestra en la ilustración siguiente, el resultado publicado incluye los siguientes cuatro archivos:</span><span class="sxs-lookup"><span data-stu-id="cd603-120">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="cd603-121">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="cd603-121">*HelloWorld.deps.json*</span></span>
      * <span data-ttu-id="cd603-122">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="cd603-122">*HelloWorld.dll*</span></span>
      * <span data-ttu-id="cd603-123">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="cd603-123">*HelloWorld.pdb* (optional for deployment)</span></span>
      * <span data-ttu-id="cd603-124">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="cd603-124">*HelloWorld.runtimeconfig.json*</span></span>

   <span data-ttu-id="cd603-125">El archivo *HelloWorld.pdb* contiene símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="cd603-125">The *HelloWorld.pdb* file contains debug symbols.</span></span> <span data-ttu-id="cd603-126">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd603-126">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   ![Ventana de la consola que muestra los archivos publicados](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="cd603-128">El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecutará en cualquier plataforma compatible con .NET Core con .NET Core instalado en el sistema.</span><span class="sxs-lookup"><span data-stu-id="cd603-128">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="cd603-129">Los usuarios pueden ejecutar la aplicación mediante la emisión del comando `dotnet HelloWorld.dll` desde una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="cd603-129">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="cd603-130">Para más información sobre cómo publicar e implementar aplicaciones de .NET Core, consulte [Implementación de aplicaciones .NET Core](../../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="cd603-130">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>
