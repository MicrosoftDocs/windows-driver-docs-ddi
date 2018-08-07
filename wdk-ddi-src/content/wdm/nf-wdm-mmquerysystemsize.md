---
UID: NF:wdm.MmQuerySystemSize
title: MmQuerySystemSize function
author: windows-driver-content
description: The MmQuerySystemSize routine returns an estimate of the amount of memory in the system.
old-location: kernel\mmquerysystemsize.htm
tech.root: kernel
ms.assetid: ca4b3154-e1a1-44d1-b085-9cb5d5ed1a4a
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: MmQuerySystemSize, MmQuerySystemSize routine [Kernel-Mode Driver Architecture], k106_9456af05-c1ea-43b0-a342-bc88a8de874b.xml, kernel.mmquerysystemsize, wdm/MmQuerySystemSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmQuerySystemSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmQuerySystemSize function


## -description


The <b>MmQuerySystemSize</b> routine returns an estimate of the amount of memory in the system.


## -parameters






## -returns



<b>MmQuerySystemSize</b> returns one of <b>MmSmallSystem</b>, <b>MmMediumSystem</b>, or <b>MmLargeSystem</b>.




## -remarks



This routine can be called during driver initialization to determine how much memory it is practical to allocate for an internal buffer. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554594">MmIsThisAnNtAsSystem</a>
 

 

