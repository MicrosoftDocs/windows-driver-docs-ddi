---
UID: NF:ntddk.MmFreeNonCachedMemory
title: MmFreeNonCachedMemory function
author: windows-driver-content
description: The MmFreeNonCachedMemory routine releases a range of noncached memory that was allocated by the MmAllocateNonCachedMemory routine.
old-location: kernel\mmfreenoncachedmemory.htm
old-project: kernel
ms.assetid: 284c7e69-50c6-4eef-bcf1-547bc7032a4a
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: MmFreeNonCachedMemory, MmFreeNonCachedMemory routine [Kernel-Mode Driver Architecture], k106_29c317c1-955e-4d0c-9e65-e1aa511c7a8d.xml, kernel.mmfreenoncachedmemory, ntddk/MmFreeNonCachedMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmFreeNonCachedMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmFreeNonCachedMemory function


## -description


The <b>MmFreeNonCachedMemory</b> routine releases a range of noncached memory that was allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554479">MmAllocateNonCachedMemory</a> routine. 


## -parameters




### -param BaseAddress [in]

Pointer to the virtual address of the memory to be freed. 


### -param NumberOfBytes [in]

Specifies the size of the range to be freed. This value must match the size passed in a preceding call to <b>MmAllocateNonCachedMemory</b>. 


## -returns



None




## -remarks



The <b>MmFreeNonCachedMemory</b> routine performs the opposite action of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554479">MmAllocateNonCachedMemory</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554479">MmAllocateNonCachedMemory</a>
 

 

