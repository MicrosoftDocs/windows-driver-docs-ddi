---
UID: NF:ntddk.PshedAllocateMemory
title: PshedAllocateMemory function
author: windows-driver-content
description: The PshedAllocateMemory function allocates a block of memory from the nonpaged pool.
old-location: whea\pshedallocatememory.htm
old-project: whea
ms.assetid: e489601e-b016-4681-97a0-78f42004909f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: whearef_e18a3aba-ca99-4b65-92de-1c6b8c740e31.xml, ntddk/PshedAllocateMemory, PshedAllocateMemory, whea.pshedallocatememory, PshedAllocateMemory function [WHEA Drivers and Applications]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Pshed.dll
apiname:
-	PshedAllocateMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PshedAllocateMemory function


## -description


The <b>PshedAllocateMemory</b> function allocates a block of memory from the nonpaged pool.


## -syntax


````
PVOID PshedAllocateMemory(
  _In_ ULONG Size
);
````


## -parameters




### -param Size [in]

The size, in bytes, of the block of memory being allocated.


## -returns


<b>PshedAllocateMemory</b> returns a pointer to the allocated block of memory, or NULL if the memory allocation fails.



## -remarks


A PSHED plug-in calls the <b>PshedAllocateMemory</b> function to allocate a block of memory. When the PSHED plug-in is done using the allocated block of memory, it calls the <a href="..\ntddk\nf-ntddk-pshedfreememory.md">PshedFreeMemory</a> function to free the memory.



## -see-also

<a href="..\ntddk\nf-ntddk-pshedfreememory.md">PshedFreeMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PshedAllocateMemory function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

