---
title: Cómo quitar los componentes .NET Runtime y SDK
description: Instrucciones para quitar los componentes .NET Core Runtime y SDK en Windows, Mac y Linux
ms.date: 07/28/2018
author: billwagner
ms.author: wiwagn
ms.openlocfilehash: 1806d1af3b10e44ccc2eff788d8958ca976fe85b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204921"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="fc02c-103">Cómo quitar los componentes .NET Core Runtime y SDK</span><span class="sxs-lookup"><span data-stu-id="fc02c-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="fc02c-104">Con el tiempo, a medida que instale versiones actualizadas del runtime y el SDK de .NET Core, es posible que quiera quitar del equipo versiones obsoletas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc02c-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="fc02c-105">Al quitar versiones anteriores de runtime puede cambiar el runtime elegido para ejecutar aplicaciones de marco compartidas, tal como se detalla en el artículo sobre [selección de la versión de .NET Core](selection.md).</span><span class="sxs-lookup"><span data-stu-id="fc02c-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

<span data-ttu-id="fc02c-106">A partir de .NET Core 2.1, la CLI de .NET tiene opciones que puede utilizar para enumerar las versiones del SDK y de runtime que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fc02c-106">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="fc02c-107">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) para ver la lista de los SDK instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fc02c-107">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="fc02c-108">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) para ver la lista de los runtimes instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fc02c-108">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="fc02c-109">En el texto siguiente se muestra el resultado típico para Windows, macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="fc02c-109">The following text shows typical output for Windows, macOS, or Linux:</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="fc02c-110">Windows</span><span class="sxs-lookup"><span data-stu-id="fc02c-110">Windows</span></span>](#tab/Windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="fc02c-111">Linux</span><span class="sxs-lookup"><span data-stu-id="fc02c-111">Linux</span></span>](#tab/Linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[<span data-ttu-id="fc02c-112">macOS</span><span class="sxs-lookup"><span data-stu-id="fc02c-112">macOS</span></span>](#tab/macOS)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

***

## <a name="uninstalling-net-core"></a><span data-ttu-id="fc02c-113">Desinstalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc02c-113">Uninstalling .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="fc02c-114">Windows</span><span class="sxs-lookup"><span data-stu-id="fc02c-114">Windows</span></span>](#tab/Windows)

<span data-ttu-id="fc02c-115">.NET Core usa el cuadro de diálogo **Agregar o quitar programas** de Windows para quitar las versiones del runtime de .NET Core y del SDK.</span><span class="sxs-lookup"><span data-stu-id="fc02c-115">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="fc02c-116">En la siguiente ilustración se muestra el cuadro de diálogo **Agregar o quitar programas** con varias versiones del runtime y SDK de .NET instaladas.</span><span class="sxs-lookup"><span data-stu-id="fc02c-116">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![Agregar o quitar programas para quitar .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="fc02c-118">Seleccione las versiones que quiera quitar de su equipo y haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="fc02c-118">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="fc02c-119">Linux</span><span class="sxs-lookup"><span data-stu-id="fc02c-119">Linux</span></span>](#tab/Linux)

<span data-ttu-id="fc02c-120">Para desinstalar .NET Core (SDK o runtime) en Linux tiene más opciones.</span><span class="sxs-lookup"><span data-stu-id="fc02c-120">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="fc02c-121">La mejor forma de desinstalar .NET Core es repetir la misma acción que se usó para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="fc02c-121">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="fc02c-122">Los detalles específicos dependerán de la distribución que elija y del método de instalación.</span><span class="sxs-lookup"><span data-stu-id="fc02c-122">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc02c-123">Para obtener información sobre las instalaciones y desinstalaciones de .NET Core en Red Hat, consulte la [Guía de introducción a Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).</span><span class="sxs-lookup"><span data-stu-id="fc02c-123">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="fc02c-124">A partir de .NET Core 2.1, no hace falta desinstalar el SDK de .NET Core al actualizarlo mediante un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fc02c-124">Starting with .NET Core 2.1, there is no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="fc02c-125">Los comandos `update` o `refresh` del administrador de paquetes quitarán automáticamente la versión anterior tras la instalación correcta de una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="fc02c-125">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="fc02c-126">Si ha instalado .NET Core con un administrador de paquetes, use ese mismo administrador de paquetes para desinstalar el SDK o el runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="fc02c-126">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="fc02c-127">Las instalaciones de .NET Core admiten los administradores de paquetes más populares.</span><span class="sxs-lookup"><span data-stu-id="fc02c-127">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="fc02c-128">Consulte la documentación del administrador de paquetes de su distribución para conocer la sintaxis exacta en su entorno:</span><span class="sxs-lookup"><span data-stu-id="fc02c-128">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="fc02c-129">[apt-get(8)](https://linux.die.net/man/8/apt-get) se utiliza en sistemas basados en Debian, incluido Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="fc02c-129">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="fc02c-130">[yum(8)](https://linux.die.net/man/8/yum) se utiliza en Fedora, CentOS y Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="fc02c-130">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="fc02c-131">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) se utiliza en openSUSE y SUSE Linux Enterprise Server (SLES).</span><span class="sxs-lookup"><span data-stu-id="fc02c-131">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="fc02c-132">[DNF(8)](https://dnf.readthedocs.io/latest/command_ref.html) se utiliza en Fedora.</span><span class="sxs-lookup"><span data-stu-id="fc02c-132">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="fc02c-133">En casi todos los casos, el comando para quitar un paquete es `remove`.</span><span class="sxs-lookup"><span data-stu-id="fc02c-133">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="fc02c-134">El nombre del paquete para la instalación del SDK de .NET Core para la mayoría de administradores de paquetes es `dotnet-sdk`, seguido por el número de versión.</span><span class="sxs-lookup"><span data-stu-id="fc02c-134">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="fc02c-135">A partir de la versión 2.1.300 del SDK de .NET Core y de la versión `2.1` del runtime, solo se requieren el primer y el segundo número de versión: por ejemplo, puede hacer referencia a la versión 2.1.300 del SDK de .NET Core como el paquete `dotnet-sdk-2.1`.</span><span class="sxs-lookup"><span data-stu-id="fc02c-135">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="fc02c-136">Para las versiones anteriores se requiere la cadena de versión completa: por ejemplo, se requeriría `dotnet-sdk-2.1.200` para la versión 2.1.200 del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc02c-136">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="fc02c-137">En los equipos en los que solo se ha instalado el runtime, y no el SDK, el nombre del paquete es `dotnet-runtime-<version>` para .NET Core Runtime y `aspnetcore-runtime-<version>` para la pila de runtime entera.</span><span class="sxs-lookup"><span data-stu-id="fc02c-137">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="fc02c-138">Al instalar las versiones de .NET Core anteriores a 2.0 no se desinstaló la aplicación host al desinstalar el SDK mediante el administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fc02c-138">.NET Core installations prior to 2.0 did not uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="fc02c-139">Al usar `apt-get`, el comando es:</span><span class="sxs-lookup"><span data-stu-id="fc02c-139">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="fc02c-140">Tenga en cuenta que no hay ninguna versión conectada a `dotnet-host`.</span><span class="sxs-lookup"><span data-stu-id="fc02c-140">Note that there is no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="fc02c-141">Si ha realizado la instalación mediante un paquete tarball, debe quitar .NET Core mediante el método manual.</span><span class="sxs-lookup"><span data-stu-id="fc02c-141">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="fc02c-142">Debe quitar los SDK y runtimes por separado, quitando el directorio que contiene dicha versión.</span><span class="sxs-lookup"><span data-stu-id="fc02c-142">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="fc02c-143">Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:</span><span class="sxs-lookup"><span data-stu-id="fc02c-143">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="fc02c-144">Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="fc02c-144">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="fc02c-145">macOS</span><span class="sxs-lookup"><span data-stu-id="fc02c-145">macOS</span></span>](#tab/macOS)

<span data-ttu-id="fc02c-146">En Mac, debe quitar los SDK y runtimes por separado, quitando el directorio que contiene dicha versión.</span><span class="sxs-lookup"><span data-stu-id="fc02c-146">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="fc02c-147">Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:</span><span class="sxs-lookup"><span data-stu-id="fc02c-147">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="fc02c-148">Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="fc02c-148">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

<span data-ttu-id="fc02c-149">A partir de .NET Core 2.1, no hace falta desinstalar el SDK de .NET Core al actualizarlo mediante un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fc02c-149">Starting with .NET Core 2.1, there is no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="fc02c-150">Los comandos `update` o `refresh` del administrador de paquetes quitarán automáticamente la versión anterior tras la instalación correcta de una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="fc02c-150">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

---