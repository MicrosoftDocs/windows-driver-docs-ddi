---
UID: NF:storport.StorPortReadRegisterBufferUlong64
title: StorPortReadRegisterBufferUlong64 macro (storport.h)
description: This StorPortReadRegisterBufferUlong64 routine reads a number of ULONG64 values from the specified 64-bit register address into a buffer.
old-location: storage\storportreadregisterbufferulong64.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortReadRegisterBufferUlong64 macro"]
ms.keywords: StorPortReadRegisterBufferUlong64, StorPortReadRegisterBufferUlong64 routine [Storage Devices], storage.storportreadregisterbufferulong64, storport/StorPortReadRegisterBufferUlong64
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortReadRegisterBufferUlong64
 - storport/StorPortReadRegisterBufferUlong64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortReadRegisterBufferUlong64
---

# StorPortReadRegisterBufferUlong64 macro


## -description

This <b>StorPortReadRegisterBufferUlong64</b> routine reads a number of <b>ULONG64</b> values from the specified 64-bit register address into a buffer.

## -parameters

### -param h 

[in]
A pointer to the hardware device extension.

### -param r 

[in]
A pointer to the register where the data is to be read. The register must be a mapped range in memory space.

### -param b 

[out]
A pointer to the buffer that receives the data that is read.

### -param c 

[in]
specifies the number of data values to read. Each data item has a size of <b>sizeof</b>(ULONG64).

## -remarks

The <b>StorPortReadRegisterBufferUlong64</b> routine is only available on the 64-bit version of Windows.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportwriteregisterbufferulong64">StorPortWriteRegisterBufferUlong64</a>
