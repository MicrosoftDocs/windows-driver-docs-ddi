---
UID: NF:storport.StorPortReadPortUshort
title: StorPortReadPortUshort macro
author: windows-driver-content
description: The StorPortReadPortUshort routine reads a value from a specified port address.
old-location: storage\storportreadportushort.htm
old-project: storage
ms.assetid: e5c9e91a-96b7-4774-8bb4-7519968ce072
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortReadPortUshort, StorPortReadPortUshort routine [Storage Devices], storage.storportreadportushort, storport/StorPortReadPortUshort, storprt_fe44d011-ae82-4255-9df9-c1d8f999fd63.xml
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
-	StorPortReadPortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadPortUshort macro


## -description


The <b>StorPortReadPortUshort</b> routine reads a value from a specified port address. 


## -parameters




### -param h

TBD


### -param p

TBD






#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Port [in]

Pointer to the address from which to read. 


## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564721">ScsiPortReadPortBufferUshort</a>. For a buffered version of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567472">StorPortReadPortBufferUshort</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564721">ScsiPortReadPortBufferUshort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567472">StorPortReadPortBufferUshort</a>
 

 

