---
UID: NF:storport.StorPortReadPortUshort
title: StorPortReadPortUshort function
author: windows-driver-content
description: The StorPortReadPortUshort routine reads a value from a specified port address.
old-location: storage\storportreadportushort.htm
old-project: storage
ms.assetid: e5c9e91a-96b7-4774-8bb4-7519968ce072
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortReadPortUshort routine [Storage Devices], storage.storportreadportushort, storprt_fe44d011-ae82-4255-9df9-c1d8f999fd63.xml, StorPortReadPortUshort, storport/StorPortReadPortUshort
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortReadPortUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadPortUshort function


## -description


The <b>StorPortReadPortUshort</b> routine reads a value from a specified port address. 


## -syntax


````
STORPORT_API USHORT StorPortReadPortUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Port
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Port [in]

Pointer to the address from which to read. 


## -returns


<b>StorPortReadPortUshort</b> returns a data item of length <b>sizeof</b>(USHORT).



## -remarks


For more information, see <a href="..\srb\nf-srb-scsiportreadportbufferushort.md">ScsiPortReadPortBufferUshort</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadportbufferushort.md">StorPortReadPortBufferUshort</a>. 



## -see-also

<a href="..\srb\nf-srb-scsiportreadportbufferushort.md">ScsiPortReadPortBufferUshort</a>

<a href="..\storport\nf-storport-storportreadportbufferushort.md">StorPortReadPortBufferUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

