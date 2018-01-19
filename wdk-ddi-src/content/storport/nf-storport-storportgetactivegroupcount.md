---
UID: NF:storport.StorPortGetActiveGroupCount
title: StorPortGetActiveGroupCount function
author: windows-driver-content
description: The StorPortGetActiveGroupCount routine returns the number of processor groups that are present in the system.
old-location: storage\storportgetactivegroupcount.htm
old-project: storage
ms.assetid: 640dd836-a5f9-4a88-b2a3-038a66a50868
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetActiveGroupCount
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
req.alt-api: StorPortGetActiveGroupCount
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

# StorPortGetActiveGroupCount function



## -description
The <b>StorPortGetActiveGroupCount</b> routine returns the number of processor groups that are present in the system.



## -syntax

````
ULONG StorPortGetActiveGroupCount(
  _In_  PVOID   HwDeviceExtension,
  _Out_ PUSHORT NumberGroups
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NumberGroups [out]

A pointer to a variable that holds the number of groups.


## -returns
The <b>StorPortGetActiveGroupCount</b> routine returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The operation was successful.

 


## -remarks
