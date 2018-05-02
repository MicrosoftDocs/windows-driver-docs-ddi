---
UID: NF:storport.StorPortWritePortUchar
title: StorPortWritePortUchar macro
author: windows-driver-content
description: The StorPortWritePortUchar routine writes a value to a specified register address.
old-location: storage\storportwriteportuchar.htm
old-project: storage
ms.assetid: 421bd075-e919-4389-af38-e0dd686f7c05
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortWritePortUchar, StorPortWritePortUchar routine [Storage Devices], storage.storportwriteportuchar, storport/StorPortWritePortUchar, storprt_602c6d78-179c-4eaa-8131-ec2be13b2050.xml
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
-	StorPortWritePortUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWritePortUchar macro


## -description


The <b>StorPortWritePortUchar</b> routine writes a value to a specified register address. 


## -parameters




### -param h

TBD


### -param p

TBD


### -param v

TBD






#### - HwDeviceExtension [in]

Pointer to the hardware device extension.


#### - Port [in]

Contains the address of the port to be written to. 


#### - Value [in]

Contains the value to be written. 


## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564834">ScsiPortWritePortUchar</a>. For a buffered equivalent of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567515">StorPortWritePortBufferUchar</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564834">ScsiPortWritePortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567515">StorPortWritePortBufferUchar</a>
 

 

