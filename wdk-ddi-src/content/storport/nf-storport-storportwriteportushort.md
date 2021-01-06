---
UID: NF:storport.StorPortWritePortUshort
title: StorPortWritePortUshort macro (storport.h)
description: The StorPortWritePortUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportushort.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortWritePortUshort macro"]
ms.keywords: StorPortWritePortUshort, StorPortWritePortUshort routine [Storage Devices], storage.storportwriteportushort, storport/StorPortWritePortUshort, storprt_7e675f67-f027-48e7-a41b-b672b0f81d20.xml
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
 - StorPortWritePortUshort
 - storport/StorPortWritePortUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWritePortUshort
---

# StorPortWritePortUshort macro


## -description

The <b>StorPortWritePortUshort</b> routine writes a value to a specified register address.

## -parameters

### -param h

<p>Pointer to the hardware device extension.</p>

### -param p

<p>Contains the address of the port to be written to. </p>

### -param v

<p>Contains the value to be written. </p>

## -remarks

For more information, see <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportushort">ScsiPortWritePortUshort</a>. For a buffered equivalent of this routine, see <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportbufferushort">StorPortWritePortBufferUshort</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportushort">ScsiPortWritePortUshort</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportbufferushort">StorPortWritePortBufferUshort</a>
