---
UID: NF:storport.StorPortReadPortUchar
title: StorPortReadPortUchar macro (storport.h)
description: The StorPortReadPortUchar routine reads a value from a specified port address
old-location: storage\storportreadportuchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortReadPortUchar macro"]
ms.keywords: StorPortReadPortUchar, StorPortReadPortUchar routine [Storage Devices], storage.storportreadportuchar, storport/StorPortReadPortUchar, storprt_de88c383-95ac-4f3e-b02d-aec76132e4c3.xml
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
 - StorPortReadPortUchar
 - storport/StorPortReadPortUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortReadPortUchar
---

# StorPortReadPortUchar macro


## -description

The <b>StorPortReadPortUchar</b> routine reads a value from a specified port address

## -parameters

### -param h 

[in]
A pointer to the hardware device extension.

### -param p 

[in]
Pointer to the address from which to read.

## -remarks

For more information, see the <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferuchar">ScsiPortReadPortBufferUchar</a> routine. For a buffered version of this routine, see <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportbufferuchar">StorPortReadPortBufferUchar</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferuchar">ScsiPortReadPortBufferUchar</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportbufferuchar">StorPortReadPortBufferUchar</a>
