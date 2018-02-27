---
UID: NF:storport.StorPortReadRegisterBufferUlong
title: StorPortReadRegisterBufferUlong macro
author: windows-driver-content
description: The StorPortReadRegisterBufferUlong routine reads a value from a specified register address.
old-location: storage\storportreadregisterbufferulong.htm
old-project: storage
ms.assetid: 069defee-6295-4492-b0bb-135c476c79aa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortReadRegisterBufferUlong, StorPortReadRegisterBufferUlong routine [Storage Devices], storage.storportreadregisterbufferulong, storport/StorPortReadRegisterBufferUlong, storprt_18f8816c-5e0f-4139-829d-d9de65d63529.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortReadRegisterBufferUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadRegisterBufferUlong macro


## -description


The <b>StorPortReadRegisterBufferUlong</b> routine reads a value from a specified register address. 


## -syntax


````
STORPORT_API VOID StorPortReadRegisterBufferUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Register,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````


## -parameters




### -param h

TBD


### -param r

TBD


### -param b

TBD


### -param c

TBD






#### - Buffer [in]

Pointer to the buffer that receives the data that is read.


#### - Count [in]

Specifies the number of data items to be read. Each data item has a size of <b>sizeof</b>(ULONG). 


#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Register [in]

Pointer to the register where the data is to be read. 


## -remarks



For more information, see <a href="..\storport\nf-storport-scsiportreadregisterbufferulong.md">ScsiPortReadRegisterBufferUlong</a>. For a nonbuffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterulong.md">StorPortReadRegisterUlong</a>.




## -see-also

<a href="..\storport\nf-storport-scsiportreadregisterbufferulong.md">ScsiPortReadRegisterBufferUlong</a>



<a href="..\storport\nf-storport-storportreadregisterulong.md">StorPortReadRegisterUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterBufferUlong routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

