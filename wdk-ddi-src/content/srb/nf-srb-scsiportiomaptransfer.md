---
UID: NF:srb.ScsiPortIoMapTransfer
title: ScsiPortIoMapTransfer function (srb.h)
description: The ScsiPortIoMapTransfer routine sets up the system DMA controller for a miniport driver to transfer data through a subordinate HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportiomaptransfer.htm
tech.root: storage
ms.assetid: 627a2d4c-22c8-48ea-b409-dc246c85a316
ms.date: 03/29/2018
keywords: ["ScsiPortIoMapTransfer function"]
ms.keywords: ScsiPortIoMapTransfer, ScsiPortIoMapTransfer routine [Storage Devices], scsiprt_9473c978-7355-4296-b8ac-07b20f6ea441.xml, srb/ScsiPortIoMapTransfer, storage.scsiportiomaptransfer
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortIoMapTransfer
 - srb/ScsiPortIoMapTransfer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortIoMapTransfer
---

# ScsiPortIoMapTransfer function


## -description

The <b>ScsiPortIoMapTransfer</b> routine sets up the system DMA controller for a miniport driver to transfer data through a subordinate HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param Srb 

[in]
Pointer to the SCSI request block for the DMA transfer.

### -param LogicalAddress 

[in]
Specifies the starting address for the transfer operation. This value can be the base address of a buffer into which or from which data is to be transferred. This value can be an offset within such a buffer.

### -param Length 

[in]
Specifies the number of bytes to be transferred.

## -returns

None

## -remarks

Only miniport drivers of HBAs that use a system DMA controller (subordinate DMA) call <b>ScsiPortIoMapTransfer</b>. This routine must be called before such a miniport driver sets up its HBA to transfer data. The range specified by the <i>LogicalAddress</i> and <i>Length</i> must be within the buffer described by the given SRB.

After the operating system-specific port driver programs the system DMA controller, it calls the miniport driver's <a href="/previous-versions/windows/hardware/drivers/ff557291(v=vs.85)">HwScsiDmaStarted</a> routine. <i>HwScsiDmaStarted</i> should program the HBA to begin the data transfer. Note that an HBA can interrupt between the miniport driver's call to <b>ScsiPortIoMapTransfer</b> and the operating system-specific port driver's call to the miniport driver's <i>HwScsiDmaStarted</i> routine.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff557291(v=vs.85)">HwScsiDmaStarted</a>



<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportflushdma">ScsiPortFlushDma</a>