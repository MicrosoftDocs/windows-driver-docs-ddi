---
UID: NF:ntddk.PshedFreeMemory
title: PshedFreeMemory function
author: windows-driver-content
description: The PshedFreeMemory function frees a block of memory that was previously allocated by calling the PshedAllocateMemory function.
old-location: whea\pshedfreememory.htm
old-project: whea
ms.assetid: e0784b46-9929-480c-88d0-9983d80fd753
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PshedFreeMemory, PshedFreeMemory function [WHEA Drivers and Applications], ntddk/PshedFreeMemory, whea.pshedfreememory, whearef_e17812c6-f817-490d-b1f7-bf5fa16d769b.xml
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
-	PshedFreeMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PshedFreeMemory function


## -description


The <b>PshedFreeMemory</b> function frees a block of memory that was previously allocated by calling the <a href="..\ntddk\nf-ntddk-pshedallocatememory.md">PshedAllocateMemory</a> function.


## -syntax


````
VOID PshedFreeMemory(
  _In_ PVOID Address
);
````


## -parameters




### -param Address [in]

A pointer to the block of memory being freed.


## -returns



None




## -remarks



A PSHED plug-in calls the <b>PshedFreeMemory</b> function to free a block of memory that it previously allocated by calling the <a href="..\ntddk\nf-ntddk-pshedallocatememory.md">PshedAllocateMemory</a> function.




## -see-also

<a href="..\ntddk\nf-ntddk-pshedallocatememory.md">PshedAllocateMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PshedFreeMemory function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

