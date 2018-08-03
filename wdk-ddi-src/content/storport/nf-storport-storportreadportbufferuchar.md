---
UID: NF:storport.StorPortReadPortBufferUchar
title: StorPortReadPortBufferUchar macro
author: windows-driver-content
description: The StorPortReadPortBufferUchar routine reads a value from a specified port address
old-location: storage\storportreadportbufferuchar.htm
tech.root: storage
ms.assetid: 8602efbf-8e90-43d3-992f-4d2ecbcc7043
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortReadPortBufferUchar, StorPortReadPortBufferUchar routine [Storage Devices], storage.storportreadportbufferuchar, storport/StorPortReadPortBufferUchar, storprt_e7304977-c32a-44c2-88ea-a08767ea5399.xml
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
-	StorPortReadPortBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadPortBufferUchar macro


## -description


The <b>StorPortReadPortBufferUchar</b> routine reads a value from a specified port address 


## -parameters




### -param h [in]

A pointer to the hardware device extension.


### -param p [in]

A pointer to the address from which to read. 


### -param b [in]

A pointer to the buffer that receives the data that is read.


### -param c [in]

Number of unsigned characters to be read. 

A ULONG containing the count. 

## -remarks



For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564715">ScsiPortReadPortBufferUchar</a> routine. For a nonbuffered version of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567474">StorPortReadPortUchar</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564715">ScsiPortReadPortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567474">StorPortReadPortUchar</a>
 

 

