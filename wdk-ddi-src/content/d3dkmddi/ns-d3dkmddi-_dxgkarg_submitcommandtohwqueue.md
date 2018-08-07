---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMANDTOHWQUEUE
title: _DXGKARG_SUBMITCOMMANDTOHWQUEUE
author: windows-driver-content
description:
ms.assetid: 914e7a49-0336-4c99-850f-95defcc4218e
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_SUBMITCOMMANDTOHWQUEUE, DXGKARG_SUBMITCOMMANDTOHWQUEUE,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SUBMITCOMMANDTOHWQUEUE
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGKARG_SUBMITCOMMANDTOHWQUEUE
product: 
- Windows
targetos: Windows
---

# _DXGKARG_SUBMITCOMMANDTOHWQUEUE structure

## -description

Arguments used to submit a command to the hardware queue.

## -struct-fields

### -field hHwQueue

[in] Hardware queue being submitted to.

### -field HwQueueProgressFenceId

Hardware queue progress fence ID that will be signaled when the Present Blt is done on the GPU.

### -field DmaBufferVirtualAddress

The virtual address of the buffer.

### -field DmaBufferSize

The size of the buffer.

### -field DmaBufferPrivateDataSize

The buffer's private data size.

### -field pDmaBufferPrivateData

The buffer private data.

### -field Flags

Flags.

