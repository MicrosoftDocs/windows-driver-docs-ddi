---
UID: NF:srb.ScsiPortLogError
title: ScsiPortLogError function (srb.h)
description: The ScsiPortLogError routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportlogerror.htm
tech.root: storage
ms.assetid: 278f4fff-6e71-4544-8838-90f659c5029e
ms.date: 03/29/2018
ms.keywords: ScsiPortLogError, ScsiPortLogError routine [Storage Devices], scsiprt_5d3ec5ab-07f8-47d1-ab0c-363639c1e8aa.xml, srb/ScsiPortLogError, storage.scsiportlogerror
f1_keywords:
 - "srb/ScsiPortLogError"
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
- ScsiPortLogError
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortLogError function


## -description


The <b>ScsiPortLogError</b> routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param OPTIONAL

<p>Pointer to a SCSI request block if one is associated with the error. Otherwise, this parameter is <b>NULL</b>.</p>


### -param PathId [in]

Identifies the SCSI bus.


### -param TargetId [in]

Identifies the target controller or device on the bus.


### -param Lun [in]

Identifies the logical unit number of the target device.


### -param ErrorCode [in]

Specifies an error code indicating one of the following values as the type of error.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SP_BAD_FW_ERROR

</td>
<td>
Indicates the driver has detected bad or old firmware. The device will not be used.

</td>
</tr>
<tr>
<td>
SP_BAD_FW_WARNING

</td>
<td>
Indicates the driver has detected a card with old or bad firmware, which can result in reduced performance or functionality.

</td>
</tr>
<tr>
<td>
SP_BUS_PARITY_ERROR

</td>
<td>
Indicates a SCSI bus parity error was detected.

</td>
</tr>
<tr>
<td>
SP_BUS_TIME_OUT

</td>
<td>
Indicates a SCSI bus connection to a logical unit timed out.

</td>
</tr>
<tr>
<td>
SP_INTERNAL_ADAPTER_ERROR

</td>
<td>
Indicates an internal HBA error was detected.

</td>
</tr>
<tr>
<td>
SP_INVALID_RESELECTION

</td>
<td>
Indicates a logical unit reselected unexpectedly or with an invalid queue tag.

</td>
</tr>
<tr>
<td>
SP_IRQ_NOT_RESPONDING

</td>
<td>
Indicates the HBA is not interrupting when expected.

</td>
</tr>
<tr>
<td>
SP_PROTOCOL_ERROR

</td>
<td>
Indicates the miniport driver detected a SCSI bus protocol error.

</td>
</tr>
<tr>
<td>
SP_REQUEST_TIMEOUT

</td>
<td>
Indicates an operation to the controller has timed out.

</td>
</tr>
<tr>
<td>
SP_UNEXPECTED_DISCONNECT

</td>
<td>
Indicates that a target disconnected unexpectedly.

</td>
</tr>
</table>
 


### -param UniqueId [in]

Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same <i>ErrorCode</i>. For some miniport drivers, this identifies the line of code where the error was detected. For others, it is additional information returned by the HBA.


## -returns



None




## -remarks



A miniport driver should log all real hardware errors. However, it should not log common operational errors, such as selection time-outs or bus resets.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportnotification">ScsiPortNotification</a>
 

 

