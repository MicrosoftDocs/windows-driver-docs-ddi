---
UID: NF:storport.StorPortWritePortUlong
title: StorPortWritePortUlong macro (storport.h)
description: The StorPortWritePortUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportulong.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortWritePortUlong macro"]
ms.keywords: StorPortWritePortUlong, StorPortWritePortUlong routine [Storage Devices], storage.storportwriteportulong, storport/StorPortWritePortUlong, storprt_4f568f62-adb7-4176-9229-e2af5d4453cb.xml
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
 - StorPortWritePortUlong
 - storport/StorPortWritePortUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWritePortUlong
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

For more information, see <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportulong">ScsiPortWritePortUlong</a>. For a buffered equivalent of this routine, see <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportbufferulong">StorPortWritePortBufferUlong</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteportulong">ScsiPortWritePortUlong</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteportbufferulong">StorPortWritePortBufferUlong</a>
