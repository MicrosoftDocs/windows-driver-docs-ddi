---
UID: NC:storport.HW_INTERRUPT
title: HW_INTERRUPT
author: windows-driver-content
description: The Storport driver calls the HwStorInterrupt routine after the HBA generates an interrupt request.
old-location: storage\hwstorinterrupt.htm
old-project: storage
ms.assetid: 3c61d947-3e05-4750-a50c-be9b2dc573f0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstorinterrupt, HwStorInterrupt routine [Storage Devices], HwStorInterrupt, HW_INTERRUPT, HW_INTERRUPT, storport/HwStorInterrupt, stormini_17f68641-1cfd-47b3-a52f-be98f96e693f.xml
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
req.irql: DIRQL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Storport.h
apiname: 
-	HwStorInterrupt
product: Windows
targetos: Windows
req.typenames: *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_INTERRUPT callback


## -description


The Storport driver calls the <b>HwStorInterrupt</b> routine after the HBA generates an interrupt request.


## -prototype


````
HW_INTERRUPT HwStorInterrupt;

BOOLEAN HwStorInterrupt(
   IN PVOID DeviceExtension
)
{ ... }
````


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area. 


## -returns


If the miniport driver finds that its HBA did not generate the interrupt, <b>HwStorInterrupt</b> should return <b>FALSE</b> as soon as possible. The <b>HwStorInterrupt</b> routine should return within 50 microseconds.



## -remarks


The name <b>HwStorInterrupt</b> is just a placeholder. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:
<pre class="syntax" xml:space="preserve"><code>typedef
BOOLEAN
HW_INTERRUPT (
  IN PVOID  DeviceExtension
  );</code></pre>The <b>HwStorInterrupt</b> routine should return within 50 microseconds, ideally as short a time as possible. Therefore, all activity does not have to occur at high IRQL should be deferred to the <a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorDpcRoutine</a> that is defined in the miniport driver and issued by using <a href="..\storport\nf-storport-storportissuedpc.md">StorPortIssueDpc</a>.  The latency of the DPC is very low, and it will be called immediately after the return from high IRQL.

The port driver calls the <b>HwStorInterrupt</b> routine at DIRQL.



## -see-also

<a href="..\storport\nf-storport-storportissuedpc.md">StorPortIssueDpc</a>

<a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorDpcRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_INTERRUPT routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

