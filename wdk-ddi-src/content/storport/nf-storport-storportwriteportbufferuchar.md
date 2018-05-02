---
UID: NF:storport.StorPortWritePortBufferUchar
title: StorPortWritePortBufferUchar macro
author: windows-driver-content
description: The StorPortWritePortBufferUchar routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferuchar.htm
old-project: storage
ms.assetid: 44b57aa2-37ef-4491-8a88-9e7f880f5c1b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortWritePortBufferUchar, StorPortWritePortBufferUchar routine [Storage Devices], storage.storportwriteportbufferuchar, storport/StorPortWritePortBufferUchar, storprt_5bdd38fc-5cb0-483e-a0aa-19179c7ad833.xml
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
-	StorPortWritePortBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWritePortBufferUchar macro


## -description


The <b>StorPortWritePortBufferUchar</b> routine writes a value to a specified register address. 


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

Contains the number of data items of size <b>sizeof</b>(UCHAR) to be written. 


#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Port [in]

Contains the address of the port to be written to. 


## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564817">ScsiPortWritePortBufferUchar</a>. For a nonbuffered equivalent of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567522">StorPortWritePortUchar</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564817">ScsiPortWritePortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567522">StorPortWritePortUchar</a>
 

 

