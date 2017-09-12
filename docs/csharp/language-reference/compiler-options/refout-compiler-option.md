---
title: -refout (Opciones del compilador de C#)
ms.date: 2017-08-08
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /refout
dev_langs:
- CSharp
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 81a2252314ef51b5dc01fddc081eb881aa4431a7
ms.openlocfilehash: b1516356bf7ec8f5716c0c4183148f675f2ffa78
ms.contentlocale: es-es
ms.lasthandoff: 08/16/2017

---

# <a name="refout-c-compiler-options"></a><span data-ttu-id="19aab-102">/refout (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="19aab-102">/refout (C# Compiler Options)</span></span>

<span data-ttu-id="19aab-103">La opción **/refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="19aab-103">The **/refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="19aab-104">Esto se traduce en `metadataPeStream` en la API de emisión.</span><span class="sxs-lookup"><span data-stu-id="19aab-104">This translates to `metadataPeStream` in the Emit API.</span></span>

## <a name="syntax"></a><span data-ttu-id="19aab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19aab-105">Syntax</span></span>

```console
/refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="19aab-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="19aab-106">Arguments</span></span>

 <span data-ttu-id="19aab-107">`filepath` La ruta de archivo del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="19aab-107">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="19aab-108">Generalmente debe coincidir con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="19aab-108">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="19aab-109">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="19aab-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="19aab-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19aab-110">Remarks</span></span>

<span data-ttu-id="19aab-111">Los ensamblados de solo metadatos tienen sus cuerpos de métodos reemplazados por un cuerpo `throw null` único, pero incluyen todos los miembros excepto los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="19aab-111">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="19aab-112">El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).</span><span class="sxs-lookup"><span data-stu-id="19aab-112">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="19aab-113">Los ensamblados de referencia incluyen un atributo `ReferenceAssembly` de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19aab-113">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="19aab-114">Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo).</span><span class="sxs-lookup"><span data-stu-id="19aab-114">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="19aab-115">Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para su ejecución (pero todavía pueden cargarse en modo de solo reflexión).</span><span class="sxs-lookup"><span data-stu-id="19aab-115">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="19aab-116">Las herramientas que se reflejan en ensamblados necesitan asegurarse de que cargan ensamblados de referencia en el modo de solo reflexión, de otro modo, recibirán un error typeload del runtime.</span><span class="sxs-lookup"><span data-stu-id="19aab-116">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="19aab-117">Los ensamblados de referencia también quitan los metadatos (miembros privados) de los ensamblados de solo metadatos:</span><span class="sxs-lookup"><span data-stu-id="19aab-117">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="19aab-118">Un ensamblado de referencia solo tiene referencias para lo que necesita en la superficie de la API.</span><span class="sxs-lookup"><span data-stu-id="19aab-118">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="19aab-119">El ensamblado real puede tener referencias adicionales relacionadas con las implementaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="19aab-119">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="19aab-120">Por ejemplo, el ensamblado de referencia de `class C { private void M() { dynamic d = 1; ... } }` no hace referencia a ningún tipo necesario para `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="19aab-120">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="19aab-121">Los miembros de función privados (métodos, propiedades y eventos) se quitan en los casos donde su retirada no afecta a la compilación de manera visible.</span><span class="sxs-lookup"><span data-stu-id="19aab-121">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="19aab-122">Si no hay ningún atributo `InternalsVisibleTo`, haga lo mismo para los miembros de función internos.</span><span class="sxs-lookup"><span data-stu-id="19aab-122">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="19aab-123">Pero todos los tipos (incluidos los tipos anidados o privados) se conservan en los ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="19aab-123">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="19aab-124">Se conservan todos los atributos (incluso los internos).</span><span class="sxs-lookup"><span data-stu-id="19aab-124">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="19aab-125">Se conservan todos los métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="19aab-125">All virtual methods are kept.</span></span> <span data-ttu-id="19aab-126">Se mantienen las implementaciones explícitas de interfaces.</span><span class="sxs-lookup"><span data-stu-id="19aab-126">Explicit interface implementations are kept.</span></span> <span data-ttu-id="19aab-127">Se conservan los eventos y propiedades que se han implementado explícitamente, ya que sus descriptores de acceso son virtuales (y por lo tanto se conservan).</span><span class="sxs-lookup"><span data-stu-id="19aab-127">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="19aab-128">Se conservan todos los campos de un struct.</span><span class="sxs-lookup"><span data-stu-id="19aab-128">All fields of a struct are kept.</span></span> <span data-ttu-id="19aab-129">(Es un candidato para el refinamiento posterior de C#-7.1)</span><span class="sxs-lookup"><span data-stu-id="19aab-129">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="19aab-130">Las opciones `/refout` y [`/refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="19aab-130">The `/refout` and [`/refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="19aab-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="19aab-131">See Also</span></span>
 <span data-ttu-id="19aab-132">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="19aab-132">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="19aab-133">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="19aab-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
