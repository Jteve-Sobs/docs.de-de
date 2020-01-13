---
title: '.NET Core SDK und Runtimeabhängigkeiten: .NET Core'
description: In diesem Artikel werden die Voraussetzungen für das Betriebssystem und die CPU-Architektur zum Installieren des .NET Core SDK und der Runtime unter Windows, Linux und macOS erläutert.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a535048fc8756b55068098ad61fdc37fc8c1f04e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74999008"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="56b6f-103">.NET Core-Abhängigkeiten und -Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56b6f-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="56b6f-104">In diesem Artikel wird erläutert, welche Betriebssysteme und CPU-Architektur von .NET Core unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="56b6f-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="56b6f-105">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="56b6f-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31tabnetcore31"></a>[<span data-ttu-id="56b6f-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="56b6f-107">Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-108">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-109">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-109">OS</span></span>                            | <span data-ttu-id="56b6f-110">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-110">Version</span></span>                        | <span data-ttu-id="56b6f-111">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="56b6f-112">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-112">Windows Client</span></span>                | <span data-ttu-id="56b6f-113">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="56b6f-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-114">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-115">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-115">Windows 10 Client</span></span>             | <span data-ttu-id="56b6f-116">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-116">Version 1607+</span></span>                  | <span data-ttu-id="56b6f-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-117">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-118">Windows Server</span></span>                | <span data-ttu-id="56b6f-119">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-119">2012 R2+</span></span>                       | <span data-ttu-id="56b6f-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-120">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-121">Nano Server</span></span>                   | <span data-ttu-id="56b6f-122">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-122">Version 1803+</span></span>                  | <span data-ttu-id="56b6f-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-123">x64, ARM32</span></span>      |

<span data-ttu-id="56b6f-124">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="56b6f-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="56b6f-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="56b6f-126">Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-127">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-128">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-128">OS</span></span>                            | <span data-ttu-id="56b6f-129">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-129">Version</span></span>                        | <span data-ttu-id="56b6f-130">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="56b6f-131">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-131">Windows Client</span></span>                | <span data-ttu-id="56b6f-132">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="56b6f-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-133">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-134">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-134">Windows 10 Client</span></span>             | <span data-ttu-id="56b6f-135">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-135">Version 1607+</span></span>                  | <span data-ttu-id="56b6f-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-136">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-137">Windows Server</span></span>                | <span data-ttu-id="56b6f-138">2012 R2 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-138">2012 R2+</span></span>                       | <span data-ttu-id="56b6f-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-139">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-140">Nano Server</span></span>                   | <span data-ttu-id="56b6f-141">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-141">Version 1803+</span></span>                  | <span data-ttu-id="56b6f-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-142">x64, ARM32</span></span>      |

<span data-ttu-id="56b6f-143">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="56b6f-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="56b6f-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="56b6f-145">Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-146">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-147">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-147">OS</span></span>                            | <span data-ttu-id="56b6f-148">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-148">Version</span></span>                        | <span data-ttu-id="56b6f-149">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="56b6f-150">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-150">Windows Client</span></span>                | <span data-ttu-id="56b6f-151">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="56b6f-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-152">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-153">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-153">Windows 10 Client</span></span>             | <span data-ttu-id="56b6f-154">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-154">Version 1607+</span></span>                  | <span data-ttu-id="56b6f-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-155">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-156">Windows Server</span></span>                | <span data-ttu-id="56b6f-157">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="56b6f-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-158">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-159">Nano Server</span></span>                   | <span data-ttu-id="56b6f-160">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-160">Version 1803+</span></span>                   | <span data-ttu-id="56b6f-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-161">x64, ARM32</span></span>      |

<span data-ttu-id="56b6f-162">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="56b6f-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="56b6f-164">Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-165">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-166">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-166">OS</span></span>                            | <span data-ttu-id="56b6f-167">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-167">Version</span></span>                        | <span data-ttu-id="56b6f-168">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="56b6f-169">Windows-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-169">Windows Client</span></span>                | <span data-ttu-id="56b6f-170">7 SP1 oder höher, 8.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="56b6f-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-171">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-172">Windows 10-Client</span><span class="sxs-lookup"><span data-stu-id="56b6f-172">Windows 10 Client</span></span>             | <span data-ttu-id="56b6f-173">Version 1607 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-173">Version 1607+</span></span>                  | <span data-ttu-id="56b6f-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-174">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-175">Windows Server</span></span>                | <span data-ttu-id="56b6f-176">2008 R2 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="56b6f-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="56b6f-177">x64, x86</span></span>        |
| <span data-ttu-id="56b6f-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="56b6f-178">Nano Server</span></span>                   | <span data-ttu-id="56b6f-179">Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-179">Version 1803+</span></span>                  | <span data-ttu-id="56b6f-180">x64,</span><span class="sxs-lookup"><span data-stu-id="56b6f-180">x64,</span></span>            |

<span data-ttu-id="56b6f-181">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="56b6f-182">Windows 7/Vista/8.1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="56b6f-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="56b6f-183">Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:</span><span class="sxs-lookup"><span data-stu-id="56b6f-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="56b6f-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="56b6f-184">Windows 7 SP1</span></span>
- <span data-ttu-id="56b6f-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="56b6f-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="56b6f-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-186">Windows 8.1</span></span>
- <span data-ttu-id="56b6f-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="56b6f-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="56b6f-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="56b6f-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="56b6f-189">Installieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="56b6f-189">Install the following:</span></span>

- <span data-ttu-id="56b6f-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)</span><span class="sxs-lookup"><span data-stu-id="56b6f-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="56b6f-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="56b6f-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="56b6f-192">Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="56b6f-193">Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt.</span><span class="sxs-lookup"><span data-stu-id="56b6f-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="56b6f-194">Installieren Sie das Programm erneut, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="56b6f-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="56b6f-195">\- oder –</span><span class="sxs-lookup"><span data-stu-id="56b6f-195">\- or -</span></span>
>
> <span data-ttu-id="56b6f-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)</span><span class="sxs-lookup"><span data-stu-id="56b6f-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31tabnetcore31"></a>[<span data-ttu-id="56b6f-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="56b6f-198">.NET Core 3.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="56b6f-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="56b6f-199">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="56b6f-200">.NET Core 3.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-201">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-202">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-202">OS</span></span>                             | <span data-ttu-id="56b6f-203">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-203">Version</span></span>               | <span data-ttu-id="56b6f-204">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="56b6f-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="56b6f-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="56b6f-206">6, 7, 8</span></span>               | <span data-ttu-id="56b6f-207">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-207">x64</span></span> |
| <span data-ttu-id="56b6f-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="56b6f-208">CentOS</span></span>                         | <span data-ttu-id="56b6f-209">7 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-209">7+</span></span>                    | <span data-ttu-id="56b6f-210">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-210">x64</span></span> |
| <span data-ttu-id="56b6f-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-211">Oracle Linux</span></span>                   | <span data-ttu-id="56b6f-212">7 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-212">7+</span></span>                    | <span data-ttu-id="56b6f-213">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-213">x64</span></span> |
| <span data-ttu-id="56b6f-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="56b6f-214">Fedora</span></span>                         | <span data-ttu-id="56b6f-215">29 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-215">29+</span></span>                   | <span data-ttu-id="56b6f-216">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-216">x64</span></span> |
| <span data-ttu-id="56b6f-217">Debian</span><span class="sxs-lookup"><span data-stu-id="56b6f-217">Debian</span></span>                         | <span data-ttu-id="56b6f-218">9 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-218">9+</span></span>                    | <span data-ttu-id="56b6f-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="56b6f-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="56b6f-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="56b6f-220">Ubuntu</span></span>                         | <span data-ttu-id="56b6f-221">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-221">16.04+</span></span>                | <span data-ttu-id="56b6f-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="56b6f-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="56b6f-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="56b6f-223">Linux Mint</span></span>                     | <span data-ttu-id="56b6f-224">18 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-224">18+</span></span>                   | <span data-ttu-id="56b6f-225">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-225">x64</span></span> |
| <span data-ttu-id="56b6f-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="56b6f-226">openSUSE</span></span>                       | <span data-ttu-id="56b6f-227">15 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-227">15+</span></span>                   | <span data-ttu-id="56b6f-228">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-228">x64</span></span> |
| <span data-ttu-id="56b6f-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="56b6f-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="56b6f-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="56b6f-230">12 SP2+</span></span>               | <span data-ttu-id="56b6f-231">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-231">x64</span></span> |
| <span data-ttu-id="56b6f-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-232">Alpine Linux</span></span>                   | <span data-ttu-id="56b6f-233">3.10 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-233">3.10+</span></span>                 | <span data-ttu-id="56b6f-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="56b6f-234">x64, ARM64</span></span> |

<span data-ttu-id="56b6f-235">Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="56b6f-236">Weitere Informationen zum Installieren von .NET Core 3.1 unter ARM64 (Kernel 4.14 oder höher) finden Sie unter [Installieren von .NET Core 3.0 unter Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="56b6f-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56b6f-237">Für die Unterstützung von ARM64 ist Linux-Kernel 4.14 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56b6f-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="56b6f-238">Einige Linux-Verteilungen erfüllen diese Anforderung, andere hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="56b6f-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="56b6f-239">So wird Ubuntu 18.04 im Gegensatz zu Ubuntu 16.04 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56b6f-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="56b6f-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="56b6f-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="56b6f-241">.NET Core 3.0 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="56b6f-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="56b6f-242">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="56b6f-243">.NET Core 3.0 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-244">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-245">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-245">OS</span></span>                             | <span data-ttu-id="56b6f-246">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-246">Version</span></span>               | <span data-ttu-id="56b6f-247">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="56b6f-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="56b6f-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="56b6f-249">6, 7, 8</span></span>               | <span data-ttu-id="56b6f-250">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-250">x64</span></span> |
| <span data-ttu-id="56b6f-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="56b6f-251">CentOS</span></span>                         | <span data-ttu-id="56b6f-252">7 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-252">7+</span></span>                    | <span data-ttu-id="56b6f-253">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-253">x64</span></span> |
| <span data-ttu-id="56b6f-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-254">Oracle Linux</span></span>                   | <span data-ttu-id="56b6f-255">7 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-255">7+</span></span>                    | <span data-ttu-id="56b6f-256">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-256">x64</span></span> |
| <span data-ttu-id="56b6f-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="56b6f-257">Fedora</span></span>                         | <span data-ttu-id="56b6f-258">29 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-258">29+</span></span>                   | <span data-ttu-id="56b6f-259">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-259">x64</span></span> |
| <span data-ttu-id="56b6f-260">Debian</span><span class="sxs-lookup"><span data-stu-id="56b6f-260">Debian</span></span>                         | <span data-ttu-id="56b6f-261">9 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-261">9+</span></span>                    | <span data-ttu-id="56b6f-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="56b6f-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="56b6f-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="56b6f-263">Ubuntu</span></span>                         | <span data-ttu-id="56b6f-264">16.04 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-264">16.04+</span></span>                | <span data-ttu-id="56b6f-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="56b6f-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="56b6f-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="56b6f-266">Linux Mint</span></span>                     | <span data-ttu-id="56b6f-267">18 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-267">18+</span></span>                   | <span data-ttu-id="56b6f-268">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-268">x64</span></span> |
| <span data-ttu-id="56b6f-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="56b6f-269">openSUSE</span></span>                       | <span data-ttu-id="56b6f-270">15 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-270">15+</span></span>                   | <span data-ttu-id="56b6f-271">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-271">x64</span></span> |
| <span data-ttu-id="56b6f-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="56b6f-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="56b6f-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="56b6f-273">12 SP2+</span></span>               | <span data-ttu-id="56b6f-274">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-274">x64</span></span> |
| <span data-ttu-id="56b6f-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-275">Alpine Linux</span></span>                   | <span data-ttu-id="56b6f-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="56b6f-276">3.8+</span></span>                  | <span data-ttu-id="56b6f-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="56b6f-277">x64, ARM64</span></span> |

<span data-ttu-id="56b6f-278">Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="56b6f-279">Weitere Informationen zum Installieren von .NET Core 3.0 unter ARM64 finden Sie unter [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installieren von .NET Core 3.0 unter Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="56b6f-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="56b6f-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="56b6f-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="56b6f-281">.NET Core 2.2 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="56b6f-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="56b6f-282">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="56b6f-283">.NET Core 2.2 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-284">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-285">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-285">OS</span></span>                             |  <span data-ttu-id="56b6f-286">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-286">Version</span></span>                |  <span data-ttu-id="56b6f-287">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="56b6f-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="56b6f-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="56b6f-289">6, 7</span></span>                   | <span data-ttu-id="56b6f-290">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-290">x64</span></span> |
| <span data-ttu-id="56b6f-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="56b6f-291">CentOS</span></span>                         |  <span data-ttu-id="56b6f-292">7</span><span class="sxs-lookup"><span data-stu-id="56b6f-292">7</span></span>                      | <span data-ttu-id="56b6f-293">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-293">x64</span></span> |
| <span data-ttu-id="56b6f-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-294">Oracle Linux</span></span>                   |  <span data-ttu-id="56b6f-295">7</span><span class="sxs-lookup"><span data-stu-id="56b6f-295">7</span></span>                      | <span data-ttu-id="56b6f-296">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-296">x64</span></span> |
| <span data-ttu-id="56b6f-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="56b6f-297">Fedora</span></span>                         |  <span data-ttu-id="56b6f-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="56b6f-298">29, 30</span></span>                 | <span data-ttu-id="56b6f-299">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-299">x64</span></span> |
| <span data-ttu-id="56b6f-300">Debian</span><span class="sxs-lookup"><span data-stu-id="56b6f-300">Debian</span></span>                         |  <span data-ttu-id="56b6f-301">9</span><span class="sxs-lookup"><span data-stu-id="56b6f-301">9</span></span>                      | <span data-ttu-id="56b6f-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-302">x64, ARM32</span></span> |
| <span data-ttu-id="56b6f-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="56b6f-303">Ubuntu</span></span>                         |  <span data-ttu-id="56b6f-304">16.04, 18.04, 18.10, 19.04</span><span class="sxs-lookup"><span data-stu-id="56b6f-304">16.04, 18.04, 18.10, 19.04</span></span>    | <span data-ttu-id="56b6f-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-305">x64, ARM32</span></span> |
| <span data-ttu-id="56b6f-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="56b6f-306">Linux Mint</span></span>                     |  <span data-ttu-id="56b6f-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="56b6f-307">17, 18</span></span>                 | <span data-ttu-id="56b6f-308">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-308">x64</span></span> |
| <span data-ttu-id="56b6f-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="56b6f-309">openSUSE</span></span>                       |  <span data-ttu-id="56b6f-310">15 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-310">15+</span></span>                    | <span data-ttu-id="56b6f-311">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-311">x64</span></span> |
| <span data-ttu-id="56b6f-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="56b6f-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="56b6f-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="56b6f-313">12 SP2+</span></span>                | <span data-ttu-id="56b6f-314">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-314">x64</span></span> |
| <span data-ttu-id="56b6f-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-315">Alpine Linux</span></span>                   |  <span data-ttu-id="56b6f-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="56b6f-316">3.8+</span></span>                   | <span data-ttu-id="56b6f-317">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-317">x64</span></span> |

<span data-ttu-id="56b6f-318">Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="56b6f-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="56b6f-320">.NET Core 2.1 behandelt Linux als ein einziges Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="56b6f-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="56b6f-321">Es gibt einen Linux-Build (pro Chiparchitektur) für unterstützte Linux-Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="56b6f-322">.NET Core 2.1 wird unter den folgenden Linux-Verteilungen und -Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-323">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-324">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="56b6f-324">OS</span></span>                             |  <span data-ttu-id="56b6f-325">Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-325">Version</span></span>                |  <span data-ttu-id="56b6f-326">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="56b6f-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="56b6f-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="56b6f-328">6, 7, 8</span></span>                | <span data-ttu-id="56b6f-329">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-329">x64</span></span> |
| <span data-ttu-id="56b6f-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="56b6f-330">CentOS</span></span>                         |  <span data-ttu-id="56b6f-331">7 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-331">7+</span></span>                     | <span data-ttu-id="56b6f-332">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-332">x64</span></span> |
| <span data-ttu-id="56b6f-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-333">Oracle Linux</span></span>                   |  <span data-ttu-id="56b6f-334">7 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-334">7+</span></span>                     | <span data-ttu-id="56b6f-335">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-335">x64</span></span> |
| <span data-ttu-id="56b6f-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="56b6f-336">Fedora</span></span>                         |  <span data-ttu-id="56b6f-337">29 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-337">29+</span></span>                    | <span data-ttu-id="56b6f-338">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-338">x64</span></span> |
| <span data-ttu-id="56b6f-339">Debian</span><span class="sxs-lookup"><span data-stu-id="56b6f-339">Debian</span></span>                         |  <span data-ttu-id="56b6f-340">9</span><span class="sxs-lookup"><span data-stu-id="56b6f-340">9</span></span>                      | <span data-ttu-id="56b6f-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-341">x64, ARM32</span></span> |
| <span data-ttu-id="56b6f-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="56b6f-342">Ubuntu</span></span>                         |  <span data-ttu-id="56b6f-343">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="56b6f-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="56b6f-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="56b6f-344">x64, ARM32</span></span> |
| <span data-ttu-id="56b6f-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="56b6f-345">Linux Mint</span></span>                     |  <span data-ttu-id="56b6f-346">17 oder höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-346">17+</span></span>                    | <span data-ttu-id="56b6f-347">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-347">x64</span></span> |
| <span data-ttu-id="56b6f-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="56b6f-348">openSUSE</span></span>                       |  <span data-ttu-id="56b6f-349">15 und höher</span><span class="sxs-lookup"><span data-stu-id="56b6f-349">15+</span></span>                    | <span data-ttu-id="56b6f-350">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-350">x64</span></span> |
| <span data-ttu-id="56b6f-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="56b6f-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="56b6f-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="56b6f-352">12 SP2+</span></span>                | <span data-ttu-id="56b6f-353">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-353">x64</span></span> |
| <span data-ttu-id="56b6f-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="56b6f-354">Alpine Linux</span></span>                   |  <span data-ttu-id="56b6f-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="56b6f-355">3.8+</span></span>                   | <span data-ttu-id="56b6f-356">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-356">x64</span></span> |

<span data-ttu-id="56b6f-357">Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="56b6f-358">Abhängigkeiten der Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="56b6f-358">Linux distribution dependencies</span></span>

<span data-ttu-id="56b6f-359">Basierend auf den Linux-Verteilungen müssen Sie möglicherweise zusätzliche Abhängigkeiten installieren.</span><span class="sxs-lookup"><span data-stu-id="56b6f-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56b6f-360">Die exakten Versionen und Namen können sich bei der von Ihnen verwendeten Linux-Verteilung leicht unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="56b6f-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="56b6f-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="56b6f-361">Ubuntu</span></span>

<span data-ttu-id="56b6f-362">Für Ubuntu-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="56b6f-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="56b6f-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="56b6f-363">liblttng-ust0</span></span>
- <span data-ttu-id="56b6f-364">libcurl3 (für 14.x und 16.x)</span><span class="sxs-lookup"><span data-stu-id="56b6f-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="56b6f-365">libcurl4 (für 18.x)</span><span class="sxs-lookup"><span data-stu-id="56b6f-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="56b6f-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="56b6f-366">libssl1.0.0</span></span>
- <span data-ttu-id="56b6f-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="56b6f-367">libkrb5-3</span></span>
- <span data-ttu-id="56b6f-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="56b6f-368">zlib1g</span></span>
- <span data-ttu-id="56b6f-369">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="56b6f-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="56b6f-370">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="56b6f-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="56b6f-371">libicu57 (für 17.X)</span><span class="sxs-lookup"><span data-stu-id="56b6f-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="56b6f-372">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="56b6f-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="56b6f-373">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="56b6f-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="56b6f-374">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="56b6f-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="56b6f-375">Die meisten Versionen von Ubuntu enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="56b6f-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="56b6f-376">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="56b6f-377">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="56b6f-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="56b6f-378">CentOS und Fedora</span><span class="sxs-lookup"><span data-stu-id="56b6f-378">CentOS and Fedora</span></span>

<span data-ttu-id="56b6f-379">Für CentOS-Verteilungen ist die Installation der folgenden Bibliotheken erforderlich:</span><span class="sxs-lookup"><span data-stu-id="56b6f-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="56b6f-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="56b6f-380">lttng-ust</span></span>
- <span data-ttu-id="56b6f-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="56b6f-381">libcurl</span></span>
- <span data-ttu-id="56b6f-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="56b6f-382">openssl-libs</span></span>
- <span data-ttu-id="56b6f-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="56b6f-383">krb5-libs</span></span>
- <span data-ttu-id="56b6f-384">libicu</span><span class="sxs-lookup"><span data-stu-id="56b6f-384">libicu</span></span>
- <span data-ttu-id="56b6f-385">zlib</span><span class="sxs-lookup"><span data-stu-id="56b6f-385">zlib</span></span>

<span data-ttu-id="56b6f-386">Für Fedora-Benutzer: Wenn Ihre Version von OpenSSL Version 1.1 oder höher entspricht, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="56b6f-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="56b6f-387">Für .NET Core 2.0 sind außerdem die folgenden Abhängigkeiten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="56b6f-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="56b6f-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="56b6f-388">libunwind</span></span>
- <span data-ttu-id="56b6f-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="56b6f-389">libuuid</span></span>

<span data-ttu-id="56b6f-390">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="56b6f-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="56b6f-391">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="56b6f-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="56b6f-392">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="56b6f-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="56b6f-393">Die meisten Versionen von CentOS und Fedora enthalten eine frühere Version von libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="56b6f-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="56b6f-394">Sie können eine neuere Version von libgdiplus installieren, indem Sie auf Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="56b6f-395">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="56b6f-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="56b6f-396">.NET Core wird von den folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56b6f-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="56b6f-397">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="56b6f-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="56b6f-398">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="56b6f-398">.NET Core Version</span></span> | <span data-ttu-id="56b6f-399">macOS</span><span class="sxs-lookup"><span data-stu-id="56b6f-399">macOS</span></span>                 | <span data-ttu-id="56b6f-400">Architekturen</span><span class="sxs-lookup"><span data-stu-id="56b6f-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="56b6f-401">3.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-401">3.1</span></span>               | <span data-ttu-id="56b6f-402">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="56b6f-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="56b6f-403">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-403">x64</span></span> | [<span data-ttu-id="56b6f-404">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56b6f-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="56b6f-405">3.0</span><span class="sxs-lookup"><span data-stu-id="56b6f-405">3.0</span></span>               | <span data-ttu-id="56b6f-406">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="56b6f-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="56b6f-407">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-407">x64</span></span> | [<span data-ttu-id="56b6f-408">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56b6f-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="56b6f-409">2.2</span><span class="sxs-lookup"><span data-stu-id="56b6f-409">2.2</span></span>               | <span data-ttu-id="56b6f-410">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="56b6f-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="56b6f-411">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-411">x64</span></span> | [<span data-ttu-id="56b6f-412">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56b6f-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="56b6f-413">2.1</span><span class="sxs-lookup"><span data-stu-id="56b6f-413">2.1</span></span>               | <span data-ttu-id="56b6f-414">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="56b6f-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="56b6f-415">x64</span><span class="sxs-lookup"><span data-stu-id="56b6f-415">x64</span></span> | [<span data-ttu-id="56b6f-416">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56b6f-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="56b6f-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="56b6f-417">libgdiplus</span></span>

<span data-ttu-id="56b6f-418">Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="56b6f-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="56b6f-419">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="56b6f-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="56b6f-420">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="56b6f-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="56b6f-421">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="56b6f-421">Next steps</span></span>

- <span data-ttu-id="56b6f-422">Installieren Sie das [.NET Core SDK](sdk.md) (einschließlich der Runtime), um Apps zu entwickeln und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="56b6f-423">Installieren Sie die [.NET Core-Runtime](runtime.md), um von anderen erstellte Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="56b6f-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>