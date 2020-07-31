---
UID: NF:srb.ScsiPortCompleteRequest
title: ScsiPortCompleteRequest function (srb.h)
description: The ScsiPortCompleteRequest routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportcompleterequest.htm
tech.root: storage
ms.assetid: 9cd17a86-6652-414d-a80d-2e61c0ac99b6
ms.date: 03/29/2018
keywords: ["ScsiPortCompleteRequest function"]
ms.keywords: ScsiPortCompleteRequest, ScsiPortCompleteRequest routine [Storage Devices], scsiprt_be6690c0-6cfa-4a71-9877-176ed2c742e8.xml, srb/ScsiPortCompleteRequest, storage.scsiportcompleterequest
f1_keywords:
 - "srb/ScsiPortCompleteRequest"
 - "ScsiPortCompleteRequest"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortCompleteRequest
targetos: Windows
req.typenames: 
---

# ScsiPortCompleteRequest function


## -description


The <b>ScsiPortCompleteRequest</b> routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param PathId [in]

Identifies the SCSI bus; SP_UNTAGGED indicates all buses controlled by the HBA.


### -param TargetId [in]

Identifies the target controller or device on the given buses; SP_UNTAGGED indicates all targets on the bus.


### -param Lun [in]

Identifies the logical unit for the given target controller or device; SP_UNTAGGED indicates all logical units for the given target controllers on the given buses.


### -param SrbStatus [in]

Specifies the completion status to be set in the <b>SrbStatus </b>member of each SRB.


## -returns



None




## -remarks



<b>ScsiPortCompleteRequest</b> can be called to complete outstanding requests after a bus reset, a device reset, or an abort, rather than calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification</a> for each outstanding request individually. After calling <b>ScsiPortCompleteRequest</b>, do not also call <b>ScsiPortNotification</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification</a>
 

 

