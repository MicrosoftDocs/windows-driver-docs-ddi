---
UID: NF:ntddk.PshedAllocateMemory
title: PshedAllocateMemory function
description: The PshedAllocateMemory function allocates a block of memory from the nonpaged pool.
old-location: whea\pshedallocatememory.htm
tech.root: whea
ms.assetid: e489601e-b016-4681-97a0-78f42004909f
ms.date: 02/20/2018
ms.keywords: PshedAllocateMemory, PshedAllocateMemory function [WHEA Drivers and Applications], ntddk/PshedAllocateMemory, whea.pshedallocatememory, whearef_e18a3aba-ca99-4b65-92de-1c6b8c740e31.xml
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Pshed.dll
api_name:
-	PshedAllocateMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# PshedAllocateMemory function


## -description


The <b>PshedAllocateMemory</b> function allocates a block of memory from the nonpaged pool.


## -parameters




### -param Size [in]

The size, in bytes, of the block of memory being allocated.


## -returns



<b>PshedAllocateMemory</b> returns a pointer to the allocated block of memory, or NULL if the memory allocation fails.




## -remarks



A PSHED plug-in calls the <b>PshedAllocateMemory</b> function to allocate a block of memory. When the PSHED plug-in is done using the allocated block of memory, it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559463">PshedFreeMemory</a> function to free the memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559463">PshedFreeMemory</a>
 

 

