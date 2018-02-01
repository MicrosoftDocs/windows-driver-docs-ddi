---
UID: NC:srb.PHW_DMA_STARTED
title: PHW_DMA_STARTED
author: windows-driver-content
description: The PHW_DMA_STARTED routine prototype declares a SCSI miniport driver routine that starts DMA for subordinate DMA device.
old-location: storage\phw_dma_started.htm
old-project: storage
ms.assetid: 2f989c46-e90e-45e1-a520-98b05ff78e73
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.phw_dma_started, (*PHW_DMA_STARTED) callback function [Storage Devices], (*PHW_DMA_STARTED), srb/(*PHW_DMA_STARTED), ide_minikr_2e265b69-67af-449a-bfef-67fbd6694cba.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	srb.h
apiname:
-	(*PHW_DMA_STARTED)
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_DMA_STARTED callback


## -description


The PHW_DMA_STARTED routine prototype declares a SCSI miniport driver routine that starts DMA for subordinate DMA device. 


## -prototype


````
typedef VOID (*PHW_DMA_STARTED)(
  _In_ PVOID DeviceExtension 
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area. 


## -returns


None



## -remarks


If the HBA is a subordinate DMA device, the SCSI miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557291">HwScsiDmaStarted</a> routine is called after the OS-specific port driver has set up the system DMA controller for a DMA transfer.

Miniport drivers that work with the StorPort driver do not support adapters that require subordinate DMA. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557291">HwScsiDmaStarted</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_DMA_STARTED callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

