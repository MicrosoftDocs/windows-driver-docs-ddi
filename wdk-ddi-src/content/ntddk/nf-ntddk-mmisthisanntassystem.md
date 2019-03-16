---
UID: NF:ntddk.MmIsThisAnNtAsSystem
title: MmIsThisAnNtAsSystem function (ntddk.h)
description: The MmIsThisAnNtAsSystem routine is obsolete for Windows XP and later versions of Windows. Use RtlGetVersion or RtlVerifyVersionInfo instead.
old-location: kernel\mmisthisanntassystem.htm
tech.root: kernel
ms.assetid: e9daafb1-16ec-4ffe-b863-6f07c4b2a9b7
ms.date: 04/30/2018
ms.keywords: MmIsThisAnNtAsSystem, MmIsThisAnNtAsSystem routine [Kernel-Mode Driver Architecture], k106_3f6077c8-2ce9-4dce-b29e-afd262be1e80.xml, kernel.mmisthisanntassystem, ntddk/MmIsThisAnNtAsSystem
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete for Windows XP and later versions of Windows. Use RtlGetVersion or RtlVerifyVersionInfo instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmIsThisAnNtAsSystem
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmIsThisAnNtAsSystem function


## -description


The <b>MmIsThisAnNtAsSystem</b> routine is <u>obsolete</u> for Windows XP and later versions of Windows. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561910">RtlGetVersion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563026">RtlVerifyVersionInfo</a> instead.

The <b>MmIsThisAnNtAsSystem </b>routine checks whether the current platform is running a server version of the NT-based operating system.


## -parameters






## -returns



If the current platform is a server, <b>MmIsThisAnNtAsSystem</b> returns <b>TRUE</b>. 




## -remarks



Drivers can use this routine during initialization, along with <b>MmQuerySystemSize</b>, for sizing estimates of how many resources to allocate. For example, if <b>MmIsThisAnNtAsSystem</b> returns <b>TRUE</b>, the caller can increase the number of threads or the number of initially allocated entries for a lookaside list that it creates in medium and large systems. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554676">MmQuerySystemSize</a>
 

 

