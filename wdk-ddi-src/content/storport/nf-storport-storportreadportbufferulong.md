---
UID: NF:storport.StorPortReadPortBufferUlong
title: StorPortReadPortBufferUlong macro (storport.h)
description: The StorPortReadPortBufferUlong routine reads a value from a specified port address.
old-location: storage\storportreadportbufferulong.htm
tech.root: storage
ms.assetid: 0b7366db-e80f-41f0-9a51-d1c139e948d8
ms.date: 03/29/2018
keywords: ["StorPortReadPortBufferUlong macro"]
ms.keywords: StorPortReadPortBufferUlong, StorPortReadPortBufferUlong routine [Storage Devices], storage.storportreadportbufferulong, storport/StorPortReadPortBufferUlong, storprt_175251c9-5c08-4f49-9b3d-a7376c04a0a7.xml
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
 - StorPortReadPortBufferUlong
 - storport/StorPortReadPortBufferUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortReadPortBufferUlong
---

# StorPortReadPortBufferUlong macro


## -description

The <b>StorPortReadPortBufferUlong</b> routine reads a value from a specified port address.

## -parameters

### -param h 

[in]
A pointer to the hardware device extension.

### -param p 

[in]
Pointer to the address from which to read.

### -param b 

[in]
A pointer to the buffer that receives the data that is read.

### -param c 

[in]
Specifies the number of data items to be read. Each data item has a size of sizeof(ULONG). 


#### - HwDeviceExtension [in]

Pointer to the hardware device extension.

## -remarks

For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferulong">ScsiPortReadPortBufferUlong</a> routine. For a nonbuffered version of this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportulong">StorPortReadPortUlong</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferulong">ScsiPortReadPortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportulong">StorPortReadPortUlong</a>

