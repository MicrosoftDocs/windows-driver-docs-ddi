---
UID: NF:ntddk.PshedFreeMemory
title: PshedFreeMemory function (ntddk.h)
description: The PshedFreeMemory function frees a block of memory that was previously allocated by calling the PshedAllocateMemory function.
old-location: whea\pshedfreememory.htm
tech.root: whea
ms.assetid: e0784b46-9929-480c-88d0-9983d80fd753
ms.date: 02/20/2018
keywords: ["PshedFreeMemory function"]
ms.keywords: PshedFreeMemory, PshedFreeMemory function [WHEA Drivers and Applications], ntddk/PshedFreeMemory, whea.pshedfreememory, whearef_e17812c6-f817-490d-b1f7-bf5fa16d769b.xml
f1_keywords:
 - "ntddk/PshedFreeMemory"
 - "PshedFreeMemory"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Pshed.dll
api_name:
- PshedFreeMemory
targetos: Windows
req.typenames: 
---

# PshedFreeMemory function


## -description


The <b>PshedFreeMemory</b> function frees a block of memory that was previously allocated by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedallocatememory">PshedAllocateMemory</a> function.


## -parameters




### -param Address [in]

A pointer to the block of memory being freed.


## -returns



None




## -remarks



A PSHED plug-in calls the <b>PshedFreeMemory</b> function to free a block of memory that it previously allocated by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedallocatememory">PshedAllocateMemory</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedallocatememory">PshedAllocateMemory</a>
 

 

