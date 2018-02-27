---
UID: NF:storport.StorPortReadPortBufferUshort
title: StorPortReadPortBufferUshort macro
author: windows-driver-content
description: The StorPortReadPortBufferUshort routine reads a value from a specified port address.
old-location: storage\storportreadportbufferushort.htm
old-project: storage
ms.assetid: 7b45811c-4e5f-4344-b0b3-15d36b912b5b
ms.author: windowsdriverdev
ms.date: 2/24/2018
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

<a href="..\storport\nf-storport-scsiportreadportbufferushort.md">ScsiPortReadPortBufferUshort</a>



<a href="..\storport\nf-storport-storportreadportushort.md">StorPortReadPortUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortBufferUshort routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

