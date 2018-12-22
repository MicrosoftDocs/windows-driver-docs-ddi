---
UID: NF:storport.StorPortWritePortUlong
title: StorPortWritePortUlong macro
description: The StorPortWritePortUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportulong.htm
tech.root: storage
ms.assetid: 7c6d61c6-40e5-46fd-8c18-1f9d89c58515
ms.date: 03/29/2018
ms.keywords: StorPortWritePortUlong, StorPortWritePortUlong routine [Storage Devices], storage.storportwriteportulong, storport/StorPortWritePortUlong, storprt_4f568f62-adb7-4176-9229-e2af5d4453cb.xml
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
-	StorPortWritePortUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWritePortUlong macro


## -description


The <b>StorPortWritePortUlong</b> routine writes a value to a specified register address. 


## -parameters




### -param h

<p>Pointer to the hardware device extension.</p>


### -param p

<p>Contains the address of the port to be written to. </p>


### -param v

<p>Contains the value to be written. </p>






## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564837">ScsiPortWritePortUlong</a>. For a buffered equivalent of this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567517">StorPortWritePortBufferUlong</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564837">ScsiPortWritePortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567517">StorPortWritePortBufferUlong</a>
 

 

