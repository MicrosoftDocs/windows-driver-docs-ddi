---
UID: NF:srb.ScsiPortLogError
title: ScsiPortLogError function
author: windows-driver-content
description: The ScsiPortLogError routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportlogerror.htm
old-project: storage
ms.assetid: 278f4fff-6e71-4544-8838-90f659c5029e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: srb/ScsiPortLogError, ScsiPortLogError, storage.scsiportlogerror, ScsiPortLogError routine [Storage Devices], scsiprt_5d3ec5ab-07f8-47d1-ab0c-363639c1e8aa.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Scsiport.lib
-	Scsiport.dll
apiname:
-	ScsiPortLogError
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# ScsiPortLogError function


## -description


The <b>ScsiPortLogError</b> routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID ScsiPortLogError(
  _In_     PVOID               HwDeviceExtension,
  _In_opt_ PSCSI_REQUEST_BLOCK Srb,
  _In_     UCHAR               PathId,
  _In_     UCHAR               TargetId,
  _In_     UCHAR               Lun,
  _In_     ULONG               ErrorCode,
  _In_     ULONG               UniqueId
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param OPTIONAL

TBD


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


#### - Srb [in, optional]

Pointer to a SCSI request block if one is associated with the error. Otherwise, this parameter is <b>NULL</b>.


## -returns


None



## -remarks


A miniport driver should log all real hardware errors. However, it should not log common operational errors, such as selection time-outs or bus resets.



## -see-also

<a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortLogError routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

