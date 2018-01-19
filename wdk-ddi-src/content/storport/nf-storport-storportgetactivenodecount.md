---
UID: NF:storport.StorPortGetActiveNodeCount
title: StorPortGetActiveNodeCount function
author: windows-driver-content
description: The StorPortGetActiveNodeCount routine returns the number of nodes that are present in the system.
old-location: storage\storportgetactivenodecount.htm
old-project: storage
ms.assetid: b981bfe7-832b-47ae-a742-c4829a6ad06b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetActiveNodeCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetActiveNodeCount
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

# StorPortGetActiveNodeCount function



## -description
The <b>StorPortGetActiveNodeCount</b> routine returns the number of nodes that are present in the system.



## -syntax

````
ULONG StorPortGetActiveNodeCount(
  _In_  PVOID  HwDeviceExtension,
  _Out_ PULONG NumberNodes
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NumberNodes [out]

A pointer to a variable that holds the number of nodes.


## -returns
The <b>StorPortGetActiveNodeCount</b>routine returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The operation was successful.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>NumberNodes</i> is set to <b>NULL</b>.

 


## -remarks
