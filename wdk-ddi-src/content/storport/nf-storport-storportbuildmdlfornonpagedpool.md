---
UID: NF:storport.StorPortBuildMdlForNonPagedPool
title: StorPortBuildMdlForNonPagedPool function
author: windows-driver-content
description: The StorPortBuildMdlForNonPagedPool routine updates the MDL to describe the associated non-paged memory.
old-location: storage\storportbuildmdlfornonpagedpool.htm
old-project: storage
ms.assetid: f22dbf1e-4b40-4294-bca5-3011f0a97644
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortBuildMdlForNonPagedPool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortBuildMdlForNonPagedPool
req.alt-loc: storport.h
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortBuildMdlForNonPagedPool function



## -description
The <b>StorPortBuildMdlForNonPagedPool</b> routine updates the MDL to describe the associated non-paged memory.



## -syntax

````
ULONG StorPortBuildMdlForNonPagedPool(
  _In_    PVOID HwDeviceExtension,
  _Inout_ PVOID Mdl
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Mdl [in, out]

A pointer to the MDL that specifies the memory buffer.


## -returns
StorPortBuildMdlForNonPagedPool returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the MDL was updated successfully.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer to the MDL is <b>NULL</b>.
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>The call was made at an invalid IRQL. 

 


## -remarks
