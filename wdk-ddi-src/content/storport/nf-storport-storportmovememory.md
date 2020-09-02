---
UID: NF:storport.StorPortMoveMemory
title: StorPortMoveMemory function (storport.h)
description: The StorPortMoveMemory routine copies memory from one buffer to another.
old-location: storage\storportmovememory.htm
tech.root: storage
ms.assetid: 5481ae5e-c28a-478e-96be-c6ec8d7f163e
ms.date: 03/29/2018
keywords: ["StorPortMoveMemory function"]
ms.keywords: StorPortMoveMemory, StorPortMoveMemory routine [Storage Devices], storage.storportmovememory, storport/StorPortMoveMemory, storprt_7af1ec0d-f1c4-4335-9b80-1aaef26afa35.xml
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
 - StorPortMoveMemory
 - storport/StorPortMoveMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortMoveMemory
---

# StorPortMoveMemory function


## -description

The <b>StorPortMoveMemory</b> routine copies memory from one buffer to another.

## -parameters

### -param WriteBuffer 

[in]
Pointer to the destination buffer.

### -param ReadBuffer 

[in]
Pointer to the source buffer.

### -param Length 

[in]
Specifies how many bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>.

## -returns

None

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportmovememory">ScsiPortMoveMemory</a>

