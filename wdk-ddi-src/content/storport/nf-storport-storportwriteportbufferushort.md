---
UID: NF:storport.StorPortWritePortBufferUshort
title: StorPortWritePortBufferUshort macro (storport.h)
description: The StorPortWritePortBufferUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferushort.htm
tech.root: storage
ms.assetid: e7b7718b-0c03-4114-8402-9657c49230ad
ms.date: 03/29/2018
keywords: ["StorPortWritePortBufferUshort macro"]
ms.keywords: StorPortWritePortBufferUshort, StorPortWritePortBufferUshort routine [Storage Devices], storage.storportwriteportbufferushort, storport/StorPortWritePortBufferUshort, storprt_831acb6e-3529-4e20-897d-e2765b6f7f53.xml
f1_keywords:
 - "storport/StorPortWritePortBufferUshort"
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
- StorPortWritePortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWritePortBufferUshort macro


## -description


The <b>StorPortWritePortBufferUshort</b> routine writes a value to a specified register address. 


## -parameters




### -param h

<p>Pointer to the hardware device extension.</p>


### -param p

<p>Contains the address of the port to be written to. </p>


### -param b

<p>Pointer to the buffer containing the data to be written. </p>


### -param c

<p>Contains the number of data items of size <b>sizeof</b>(USHORT) to be written. </p>






## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportbufferushort">ScsiPortWritePortBufferUshort</a>. For a non-buffered equivalent of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportushort">StorPortWritePortUshort</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportbufferushort">ScsiPortWritePortBufferUshort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportushort">StorPortWritePortUshort</a>
 

 

