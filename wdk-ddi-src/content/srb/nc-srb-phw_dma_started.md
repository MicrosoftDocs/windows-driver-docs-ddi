---
UID: NC:srb.PHW_DMA_STARTED
title: PHW_DMA_STARTED (srb.h)
description: The PHW_DMA_STARTED routine prototype declares a SCSI miniport driver routine that starts DMA for subordinate DMA device.
old-location: storage\phw_dma_started.htm
tech.root: storage
ms.assetid: 2f989c46-e90e-45e1-a520-98b05ff78e73
ms.date: 03/29/2018
keywords: ["PHW_DMA_STARTED callback"]
ms.keywords: "(*PHW_DMA_STARTED), (*PHW_DMA_STARTED) callback function [Storage Devices], ide_minikr_2e265b69-67af-449a-bfef-67fbd6694cba.xml, srb/(*PHW_DMA_STARTED), storage.phw_dma_started"
f1_keywords:
 - "srb/(*PHW_DMA_STARTED)"
 - "(*PHW_DMA_STARTED)"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
req.target-type: Desktop
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
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- srb.h
api_name:
- (*PHW_DMA_STARTED)
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_DMA_STARTED callback


## -description


The PHW_DMA_STARTED routine prototype declares a SCSI miniport driver routine that starts DMA for subordinate DMA device.


## -parameters




### -param DeviceExtension 
[in]
Pointer to the miniport driver's per-HBA storage area.


## -remarks



If the HBA is a subordinate DMA device, the SCSI miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557291(v=vs.85)">HwScsiDmaStarted</a> routine is called after the OS-specific port driver has set up the system DMA controller for a DMA transfer.

Miniport drivers that work with the StorPort driver do not support adapters that require subordinate DMA.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557291(v=vs.85)">HwScsiDmaStarted</a>
 

 

