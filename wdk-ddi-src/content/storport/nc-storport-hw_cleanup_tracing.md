---
UID: NC:storport.HW_CLEANUP_TRACING
title: HW_CLEANUP_TRACING
author: windows-driver-content
description: The HwStorCleanupTracing callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.
old-location: storage\hwstorcleanuptracing.htm
old-project: storage
ms.assetid: 878a7c4f-8584-4de2-9a32-f1c358d9b27f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstorcleanuptracing, HwStorCleanupTracing routine [Storage Devices], HwStorCleanupTracing, HW_CLEANUP_TRACING, HW_CLEANUP_TRACING, storport/HwStorCleanupTracing, storvmini_7a5c9359-04e5-4ad4-b638-14cce4087df2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorCleanupTracing
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_CLEANUP_TRACING callback


## -description


The <b>HwStorCleanupTracing</b> callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.


## -prototype


````
HW_CLEANUP_TRACING HwStorCleanupTracing;

VOID HwStorCleanupTracing(
   IN PVOID Arg1
)
{ ... }
````


## -parameters




### -param Arg1

A pointer to the driver object.


## -returns


None



## -remarks


The name <b>HwStorCleanupTracing</b> is  placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_CLEANUP_TRACING (
  IN PVOID  Arg1
  );</pre>
</td>
</tr>
</table></span></div>The port driver calls the Storport virtual miniport's <b>HwStorCleanupTracing</b> at PASSIVE_LEVEL.


