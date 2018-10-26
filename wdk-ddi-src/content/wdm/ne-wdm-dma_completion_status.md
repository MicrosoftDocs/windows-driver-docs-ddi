---
UID: NE:wdm.DMA_COMPLETION_STATUS
title: DMA_COMPLETION_STATUS
author: windows-driver-content
description: The DMA_COMPLETION_STATUS enumeration describes the completion status of a DMA transfer.
old-location: kernel\dma_completion_status.htm
tech.root: kernel
ms.assetid: 12F6E1F5-15F9-42BE-8C47-C9A561513717
ms.date: 04/30/2018
ms.keywords: DMA_COMPLETION_STATUS, DMA_COMPLETION_STATUS enumeration [Kernel-Mode Driver Architecture], DmaAborted, DmaCancelled, DmaComplete, DmaError, kernel.dma_completion_status, wdm/DMA_COMPLETION_STATUS, wdm/DmaAborted, wdm/DmaCancelled, wdm/DmaComplete, wdm/DmaError
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DMA_COMPLETION_STATUS
product:
- Windows
targetos: Windows
req.typenames: DMA_COMPLETION_STATUS
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



The <i>Status</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a> routine is a <b>DMA_COMPLETION_STATUS</b>  enumeration value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>
 

 

