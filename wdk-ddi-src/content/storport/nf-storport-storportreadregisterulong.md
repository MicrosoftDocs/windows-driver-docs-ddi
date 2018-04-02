---
UID: NF:storport.StorPortReadRegisterUlong
title: StorPortReadRegisterUlong macro
author: windows-driver-content
description: The StorPortReadRegisterUlong routine reads a value from a specified register address.
old-location: storage\storportreadregisterulong.htm
old-project: storage
ms.assetid: 308e6401-9726-4333-bde8-1aec9558c5fb
ms.author: windowsdriverdev
ms.date: 3/29/2018
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



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564742">ScsiPortReadRegisterUlong</a>. For a buffered version of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567480">StorPortReadRegisterBufferUlong</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564742">ScsiPortReadRegisterUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567480">StorPortReadRegisterBufferUlong</a>
 

 

