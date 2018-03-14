---
UID: NF:storport.StorPortReadPortBufferUshort
title: StorPortReadPortBufferUshort macro
author: windows-driver-content
description: The StorPortReadPortBufferUshort routine reads a value from a specified port address.
old-location: storage\storportreadportbufferushort.htm
old-project: storage
ms.assetid: 7b45811c-4e5f-4344-b0b3-15d36b912b5b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadPortBufferUshort, StorPortReadPortBufferUshort routine [Storage Devices], storage.storportreadportbufferushort, storport/StorPortReadPortBufferUshort, storprt_8bb9a625-864a-4566-a570-87425b6bc9af.xml
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
-	StorPortReadPortBufferUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadPortBufferUshort macro


## -description


The <b>StorPortReadPortBufferUshort</b> routine reads a value from a specified port address. 


## -syntax


````
STORPORT_API VOID StorPortReadPortBufferUshort(
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

Pointer to the buffer that receives the data that is read.


#### - Count [in]

Number of data items to be read. Each data item has a size of <b>sizeof</b>(USHORT). 


#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Port [in]

Pointer to the address from which to read. 


## -remarks



For more information, see <a href="..\storport\nf-storport-scsiportreadportbufferushort.md">ScsiPortReadPortBufferUshort</a>. For a nonbuffered version of this routine, see <a href="..\storport\nf-storport-storportreadportushort.md">StorPortReadPortUshort</a>. 




## -see-also

<a href="..\storport\nf-storport-storportreadportushort.md">StorPortReadPortUshort</a>



<a href="..\storport\nf-storport-scsiportreadportbufferushort.md">ScsiPortReadPortBufferUshort</a>



 

 


