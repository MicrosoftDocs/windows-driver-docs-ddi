---
UID: NF:ntddk.KeQueryActiveProcessors
title: KeQueryActiveProcessors function (ntddk.h)
description: The KeQueryActiveProcessors routine returns a bitmask of the currently active processors.
old-location: kernel\kequeryactiveprocessors.htm
tech.root: kernel
ms.assetid: 3a7e50e9-0aeb-46e8-a1d2-7267df4921ad
ms.date: 04/30/2018
keywords: ["KeQueryActiveProcessors function"]
ms.keywords: KeQueryActiveProcessors, KeQueryActiveProcessors routine [Kernel-Mode Driver Architecture], k105_963f6993-c875-4939-89ce-7abf2e7a9c22.xml, kernel.kequeryactiveprocessors, wdm/KeQueryActiveProcessors
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeApcLte1, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - KeQueryActiveProcessors
 - ntddk/KeQueryActiveProcessors
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeQueryActiveProcessors
---

# KeQueryActiveProcessors function (ntddk.h)


## -description

The <b>KeQueryActiveProcessors</b> routine returns a bitmask of the currently active processors.

## -returns

<b>KeQueryActiveProcessors</b> returns a [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value that represents the set of currently active processors.

## -remarks

Callers cannot assume that <b>KeQueryActiveProcessors</b> maps processors to bits consecutively, or that the routine consistently uses the same mapping each time it is called. The only valid use for the return value is to determine the number of active processors by counting the number of bits that are set.

Callers must also be aware that the value returned by <b>KeQueryActiveProcessors</b> can change during runtime on versions of Windows that support hot-add CPU functionality.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerygroupaffinity">KeQueryGroupAffinity</a> routine, which specifies a processor group, instead of <b>KeQueryActiveProcessors</b>, which does not. However, the implementation of <b>KeQueryActiveProcessors</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, <b>KeQueryActiveProcessors</b> returns an affinity mask that specifies the set of active logical processors in group 0.

In Windows Vista and later versions of Windows, this routine can be called at any IRQL. However, in Windows Server 2003 and earlier versions of Windows, this routine must be called at IRQL <= APC_LEVEL.

The <b>KeNumberProcessors</b> kernel variable is obsolete in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of Windows. <b>KeNumberProcessors</b> does not appear in WDK headers for WDK releases starting with Windows Vista SP1; however, the variable is still exported from the kernel, so drivers built for earlier platforms will not break

Windows Server 2008 includes support for <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/dynamic-hardware-partitioning-architecture">Dynamic Hardware Partitioning</a> (DHP) in the Windows Datacenter and Enterprise Edition SKUs. As part of DHP, Windows Server 2008 supports hot adding CPUs at runtime. In a hot-add CPU environment, the number of processors may not remain constant during runtime.

Accordingly, in Windows Server 2008, code that can determine the number of processors must use <b>KeQueryActiveProcessors</b> instead of direct references to the kernel variable, <b>KeNumberProcessors</b>.

Review any code that currently references <b>KeNumberProcessors</b> to make sure that it accommodates changes to CPU count in hot-add CPU environments.

You can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/pnpcpu">PNPCPU</a> tool to simulate hot adding a CPU for testing purposes.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>#if (NTDDI_VERSION >= NTDDI_VISTA)
extern NTSYSAPI volatile CCHAR KeNumberProcessors;
#else
#if (NTDDI_VERSION >= NTDDI_WINXP)
extern NTSYSAPI CCHAR KeNumberProcessors;
#else
extern PCCHAR KeNumberProcessors;
#endif
#endif</pre>
</td>
</tr>
</table></span></div>
Starting with Windows XP, <b>KeNumberProcessors</b> is an 8-bit integer value that indicates the number of processors in the platform. In earlier versions of Windows, <b>KeNumberProcessors</b> is a pointer to an 8-bit integer value that indicates the number of processors in the platform.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryactiveprocessorcount">KeQueryActiveProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerygroupaffinity">KeQueryGroupAffinity</a>

