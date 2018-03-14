---
UID: NF:storport.StorPortReadRegisterUlong
title: StorPortReadRegisterUlong macro
author: windows-driver-content
description: The StorPortReadRegisterUlong routine reads a value from a specified register address.
old-location: storage\storportreadregisterulong.htm
old-project: storage
ms.assetid: 308e6401-9726-4333-bde8-1aec9558c5fb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadRegisterUlong, StorPortReadRegisterUlong routine [Storage Devices], storage.storportreadregisterulong, storport/StorPortReadRegisterUlong, storprt_dd719ccb-d625-4820-a371-dff748037a99.xml
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
-	StorPortReadRegisterUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadRegisterUlong macro


## -description


The <b>StorPortReadRegisterUlong</b> routine reads a value from a specified register address. 


## -syntax


````
STORPORT_API ULONG StorPortReadRegisterUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Register
);
````


## -parameters




### -param h

TBD


### -param r

TBD






#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Register [in]

Pointer to the register where the data is to be read. 


## -remarks



For more information, see <a href="..\storport\nf-storport-scsiportreadregisterulong.md">ScsiPortReadRegisterUlong</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterbufferulong.md">StorPortReadRegisterBufferUlong</a>.




## -see-also

<a href="..\storport\nf-storport-scsiportreadregisterulong.md">ScsiPortReadRegisterUlong</a>



<a href="..\storport\nf-storport-storportreadregisterbufferulong.md">StorPortReadRegisterBufferUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterUlong routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

