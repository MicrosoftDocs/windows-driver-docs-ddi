---
UID: NF:storport.StorPortWritePortBufferUchar
title: StorPortWritePortBufferUchar macro (storport.h)
description: The StorPortWritePortBufferUchar routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferuchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortWritePortBufferUchar macro"]
ms.keywords: StorPortWritePortBufferUchar, StorPortWritePortBufferUchar routine [Storage Devices], storage.storportwriteportbufferuchar, storport/StorPortWritePortBufferUchar, storprt_5bdd38fc-5cb0-483e-a0aa-19179c7ad833.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortWritePortBufferUchar
 - storport/StorPortWritePortBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWritePortBufferUchar
---

# StorPortWritePortBufferUchar macro


## -description

The <b>StorPortWritePortBufferUchar</b> routine writes a value to a specified register address.

## -parameters

### -param h

<p>Pointer to the hardware device extension.</p>

### -param p

<p>Contains the address of the port to be written to. </p>

### -param b

<p>Pointer to the buffer containing the data to be written. </p>

### -param c

<p>Contains the number of data items of size <b>sizeof</b>(UCHAR) to be written. </p>

## -remarks

For more information, see <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportbufferuchar">ScsiPortWritePortBufferUchar</a>. For a nonbuffered equivalent of this routine, see <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportuchar">StorPortWritePortUchar</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportbufferuchar">ScsiPortWritePortBufferUchar</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportuchar">StorPortWritePortUchar</a>
