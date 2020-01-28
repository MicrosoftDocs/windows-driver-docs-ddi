---
UID: NF:storport.StorPortWritePortBufferUlong
title: StorPortWritePortBufferUlong macro (storport.h)
description: The StorPortWritePortBufferUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferulong.htm
tech.root: storage
ms.assetid: 24735e9a-d259-48d1-8efe-8ff1642b6a35
ms.date: 03/29/2018
ms.keywords: StorPortWritePortBufferUlong, StorPortWritePortBufferUlong routine [Storage Devices], storage.storportwriteportbufferulong, storport/StorPortWritePortBufferUlong, storprt_7ab33563-108d-4d20-8205-c3f5ac790f59.xml
f1_keywords:
 - "storport/StorPortWritePortBufferUlong"
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
- StorPortWritePortBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWritePortBufferUlong macro


## -description


The <b>StorPortWritePortBufferUlong</b> routine writes a value to a specified register address. 


## -parameters




### -param h

<p>Pointer to the hardware device extension.</p>


### -param p

<p>Contains the address of the port to be written to. </p>


### -param b

<p>Pointer to the buffer containing the data to be written. </p>


### -param c

<p>Contains the number of data items of size <b>sizeof</b>(ULONG) to be written. </p>






## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportbufferulong">ScsiPortWritePortBufferUlong</a>. For a nonbuffered equivalent of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportulong">StorPortWritePortUlong</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportbufferulong">ScsiPortWritePortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportulong">StorPortWritePortUlong</a>
 

 

