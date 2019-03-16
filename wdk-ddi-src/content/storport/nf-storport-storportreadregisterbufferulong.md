---
UID: NF:storport.StorPortReadRegisterBufferUlong
title: StorPortReadRegisterBufferUlong macro (storport.h)
description: The StorPortReadRegisterBufferUlong routine reads a value from a specified register address.
old-location: storage\storportreadregisterbufferulong.htm
tech.root: storage
ms.assetid: 069defee-6295-4492-b0bb-135c476c79aa
ms.date: 03/29/2018
ms.keywords: StorPortReadRegisterBufferUlong, StorPortReadRegisterBufferUlong routine [Storage Devices], storage.storportreadregisterbufferulong, storport/StorPortReadRegisterBufferUlong, storprt_18f8816c-5e0f-4139-829d-d9de65d63529.xml
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortReadRegisterBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadRegisterBufferUlong macro


## -description


The <b>StorPortReadRegisterBufferUlong</b> routine reads a value from a specified register address. 


## -parameters




### -param h [in]

A pointer to the hardware device extension.


### -param r [in]


Pointer to the register where the data is to be read. 


### -param b [in]

Pointer to the buffer that receives the data that is read.


### -param c [in]

Specifies the number of data items to be read. Each data item has a size of <b>sizeof</b>(ULONG). 



## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564735">ScsiPortReadRegisterBufferUlong</a>. For a nonbuffered version of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567485">StorPortReadRegisterUlong</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564735">ScsiPortReadRegisterBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567485">StorPortReadRegisterUlong</a>
 

 

