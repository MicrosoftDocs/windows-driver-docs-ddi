---
UID: NE:wdm.__unnamed_enum_10
title: DMA_COMPLETION_STATUS (wdm.h)
description: The DMA_COMPLETION_STATUS enumeration describes the completion status of a DMA transfer.
old-location: kernel\dma_completion_status.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["DMA_COMPLETION_STATUS enumeration"]
ms.keywords: DMA_COMPLETION_STATUS, DMA_COMPLETION_STATUS enumeration [Kernel-Mode Driver Architecture], DmaAborted, DmaCancelled, DmaComplete, DmaError, kernel.dma_completion_status, wdm/DMA_COMPLETION_STATUS, wdm/DmaAborted, wdm/DmaCancelled, wdm/DmaComplete, wdm/DmaError
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.typenames: DMA_COMPLETION_STATUS
f1_keywords:
 - DMA_COMPLETION_STATUS
 - wdm/DMA_COMPLETION_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - DMA_COMPLETION_STATUS
---

# DMA_COMPLETION_STATUS enumeration


## -description

The <b>DMA_COMPLETION_STATUS</b> enumeration describes the completion status of a DMA transfer.

## -enum-fields

### -field DmaComplete

The DMA transfer completed successfully.

### -field DmaAborted

Not used.

### -field DmaError

The DMA transfer did not complete successfully because an error occurred.

### -field DmaCancelled

The DMA transfer did not complete successfully because the client canceled the transfer.

## -remarks

The <i>Status</i> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-dma_completion_routine">DmaCompletionRoutine</a> routine is a <b>DMA_COMPLETION_STATUS</b>  enumeration value.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-dma_completion_routine">DmaCompletionRoutine</a>
