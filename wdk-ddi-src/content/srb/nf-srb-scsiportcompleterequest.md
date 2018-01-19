---
UID: NF:srb.ScsiPortCompleteRequest
title: ScsiPortCompleteRequest function
author: windows-driver-content
description: The ScsiPortCompleteRequest routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportcompleterequest.htm
old-project: storage
ms.assetid: 9cd17a86-6652-414d-a80d-2e61c0ac99b6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiPortCompleteRequest
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
req.alt-api: ScsiPortCompleteRequest
req.alt-loc: Scsiport.lib,Scsiport.dll
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
req.typenames: *PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# ScsiPortCompleteRequest function



## -description
The <b>ScsiPortCompleteRequest</b> routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.



## -syntax

````
VOID ScsiPortCompleteRequest(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ UCHAR SrbStatus
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


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
<b>ScsiPortCompleteRequest</b> can be called to complete outstanding requests after a bus reset, a device reset, or an abort, rather than calling <a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a> for each outstanding request individually. After calling <b>ScsiPortCompleteRequest</b>, do not also call <b>ScsiPortNotification</b>. 


## -see-also
<dl>
<dt>
<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortCompleteRequest routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

