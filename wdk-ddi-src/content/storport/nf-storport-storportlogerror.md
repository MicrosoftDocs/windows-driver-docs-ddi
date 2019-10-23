---
UID: NF:storport.StorPortLogError
title: StorPortLogError function (storport.h)
description: The StorPortLogError routine notifies the port driver that an error occurred.
old-location: storage\storportlogerror.htm
tech.root: storage
ms.assetid: f653e6bf-e99b-4aa2-aa54-d7482d326720
ms.date: 03/29/2018
ms.keywords: StorPortLogError, StorPortLogError routine [Storage Devices], storage.storportlogerror, storport/StorPortLogError, storprt_0eb9851c-bfce-49aa-a22b-3d16a72b3dde.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortLogError"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortDeprecated
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortLogError
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortLogError function


## -description


The <b>StorPortLogError</b> routine notifies the port driver that an error occurred. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param Srb [in, optional]

Pointer to a SCSI request block if one is associated with the error. Otherwise, this parameter is <b>NULL</b>. 


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

Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same <i>ErrorCode</i> value. For some miniport drivers, this identifies the line of code where the error was detected. For others, it is additional information returned by the HBA. 


## -returns



None 




## -remarks



The port driver will log an error to the system event log.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportlogerror">ScsiPortLogError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportlogsystemevent">StorPortLogSystemEvent</a>
 

 

