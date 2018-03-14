---
UID: NF:srb.ScsiPortFlushDma
title: ScsiPortFlushDma function
author: windows-driver-content
description: The ScsiPortFlushDma routine flushes any data cached in the system DMA controller at the end of a transfer or terminates a system DMA transfer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportflushdma.htm
old-project: storage
ms.assetid: 9cf4286b-1ff7-4113-a2dc-d8813c633dd6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortFlushDma, ScsiPortFlushDma routine [Storage Devices], scsiprt_3c2fc1a8-0f37-4735-a9b8-dcec220ee5bf.xml, srb/ScsiPortFlushDma, storage.scsiportflushdma
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortFlushDma
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---

# ScsiPortFlushDma function


## -description


The <b>ScsiPortFlushDma</b> routine flushes any data cached in the system DMA controller at the end of a transfer or terminates a system DMA transfer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID ScsiPortFlushDma(
  _In_ PVOID DeviceExtension
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


## -returns



None




## -remarks



Only miniport drivers of subordinate HBAs that use a system DMA controller call this routine.

<b>ScsiPortFlushDma</b> must be called after a subordinate DMA transfer operation is completed but before the SRB is completed or the next call is made to <a href="..\srb\nf-srb-scsiportiomaptransfer.md">ScsiPortIoMapTransfer</a> for the current buffer.

<b>ScsiPortFlushDma</b> also must be called after <b>ScsiPortIoMapTransfer</b> to cancel a DMA operation, even if no transfer has occurred and the driver's <a href="..\srb\nc-srb-phw_dma_started.md">HwScsiDmaStarted</a> routine has not yet been called.




## -see-also

<a href="..\srb\nf-srb-scsiportiomaptransfer.md">ScsiPortIoMapTransfer</a>



<a href="..\srb\nc-srb-phw_dma_started.md">HwScsiDmaStarted</a>



 

 


