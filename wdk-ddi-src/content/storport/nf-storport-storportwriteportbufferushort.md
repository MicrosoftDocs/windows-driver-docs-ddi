---
UID: NF:storport.StorPortWritePortBufferUshort
title: StorPortWritePortBufferUshort macro
author: windows-driver-content
description: The StorPortWritePortBufferUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferushort.htm
old-project: storage
ms.assetid: e7b7718b-0c03-4114-8402-9657c49230ad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortWritePortBufferUshort, StorPortWritePortBufferUshort routine [Storage Devices], storage.storportwriteportbufferushort, storport/StorPortWritePortBufferUshort, storprt_831acb6e-3529-4e20-897d-e2765b6f7f53.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortWritePortBufferUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWritePortBufferUshort macro


## -description


The <b>StorPortWritePortBufferUshort</b> routine writes a value to a specified register address. 


## -syntax


````
STORPORT_API VOID StorPortWritePortBufferUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Port,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````


## -parameters




### -param h

TBD


### -param p

TBD


### -param b

TBD


### -param c

TBD






#### - Buffer [in]

Pointer to the buffer containing the data to be written. 


#### - Count [in]

Contains the number of data items of size <b>sizeof</b>(USHORT) to be written. 


#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Port [in]

Contains the address of the port to be written to. 


## -remarks



For more information, see <a href="..\storport\nf-storport-scsiportwriteportbufferushort.md">ScsiPortWritePortBufferUshort</a>. For a non-buffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportushort.md">StorPortWritePortUshort</a>. 




## -see-also

<a href="..\storport\nf-storport-storportwriteportushort.md">StorPortWritePortUshort</a>



<a href="..\storport\nf-storport-scsiportwriteportbufferushort.md">ScsiPortWritePortBufferUshort</a>



 

 


