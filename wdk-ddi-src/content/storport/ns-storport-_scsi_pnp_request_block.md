---
UID: NS:storport._SCSI_PNP_REQUEST_BLOCK
title: "_SCSI_PNP_REQUEST_BLOCK"
author: windows-driver-content
description: TheSCSI_PNP_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for plug and play (PNP) requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsi_pnp_request_block.htm
old-project: storage
ms.assetid: 0627065b-62c2-4df8-973c-b4fb5811296e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSCSI_PNP_REQUEST_BLOCK, PSCSI_PNP_REQUEST_BLOCK, PSCSI_PNP_REQUEST_BLOCK structure pointer [Storage Devices], SCSI_PNP_REQUEST_BLOCK, SCSI_PNP_REQUEST_BLOCK structure [Storage Devices], StorFilterResourceRequirements, StorQueryCapabilities, StorQueryResourceRequirements, StorRemoveDevice, StorStartDevice, StorStopDevice, StorSupriseRemoval, _SCSI_PNP_REQUEST_BLOCK, storage.scsi_pnp_request_block, storport/PSCSI_PNP_REQUEST_BLOCK, storport/SCSI_PNP_REQUEST_BLOCK, structs-storport_d08ea849-f1d6-4584-b6a4-df7127f6873d.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Minitape.h, Srb.h
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	SCSI_PNP_REQUEST_BLOCK
product: Windows
targetos: Windows
req.typenames: SCSI_PNP_REQUEST_BLOCK, *PSCSI_PNP_REQUEST_BLOCK
---

# _SCSI_PNP_REQUEST_BLOCK structure


## -description


The<b>SCSI_PNP_REQUEST_BLOCK</b> structure is a special version of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> that is used for plug and play (PNP) requests.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

The size, in bytes, of the <b>SCSI_PNP_REQUEST_BLOCK</b> structure. 


### -field Function

The operation to perform. For the <b>SCSI_PNP_REQUEST_BLOCK</b> structure, this member is always set to SRB_FUNCTION_PNP. 


### -field SrbStatus

The status of the completed request. The miniport driver should set this value before notifying the Storport driver that the request has completed. A miniport driver notifies the Storport driver that the request has completed by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a> routine with a notification type of <b>RequestComplete</b>. For a list of possible status values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>.  


### -field PnPSubFunction

This member is not currently used. Miniport drivers ignore this member. 


### -field PathId

The SCSI port or bus identifier for the request. This value is zero based. 


### -field TargetId

The target controller or device identifier on the bus. 


### -field Lun

The logical unit number (LUN) of the device. 


### -field PnPAction

The plug and play action to perform. This member can have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="StorStartDevice"></a><a id="storstartdevice"></a><a id="STORSTARTDEVICE"></a><dl>
<dt><b>StorStartDevice</b></dt>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
Start the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorRemoveDevice"></a><a id="storremovedevice"></a><a id="STORREMOVEDEVICE"></a><dl>
<dt><b>StorRemoveDevice</b></dt>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Remove the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorStopDevice"></a><a id="storstopdevice"></a><a id="STORSTOPDEVICE"></a><dl>
<dt><b>StorStopDevice</b></dt>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Stop the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorQueryCapabilities"></a><a id="storquerycapabilities"></a><a id="STORQUERYCAPABILITIES"></a><dl>
<dt><b>StorQueryCapabilities</b></dt>
<dt>0x09</dt>
</dl>
</td>
<td width="60%">
Query the capabilities of the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorQueryResourceRequirements"></a><a id="storqueryresourcerequirements"></a><a id="STORQUERYRESOURCEREQUIREMENTS"></a><dl>
<dt><b>StorQueryResourceRequirements</b></dt>
<dt>0x0B</dt>
</dl>
</td>
<td width="60%">
Query the resource requirements for the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorFilterResourceRequirements"></a><a id="storfilterresourcerequirements"></a><a id="STORFILTERRESOURCEREQUIREMENTS"></a><dl>
<dt><b>StorFilterResourceRequirements</b></dt>
<dt>0x0D</dt>
</dl>
</td>
<td width="60%">
Filter the resource requirements for the device. 

</td>
</tr>
<tr>
<td width="40%"><a id="StorSupriseRemoval"></a><a id="storsupriseremoval"></a><a id="STORSUPRISEREMOVAL"></a><dl>
<dt><b>StorSupriseRemoval</b></dt>
<dt>0x17</dt>
</dl>
</td>
<td width="60%">
Surprise Removal of the device. This value was added in Windows 7.

</td>
</tr>
</table>
 


### -field SrbFlags

Miniport driver should ignore this member. 


### -field DataTransferLength

Miniport driver should ignore this member. 


### -field TimeOutValue

The interval, in seconds, that the request can execute before the Storport driver determines that the request has timed out. 


### -field DataBuffer

Miniport driver should ignore this member. 


### -field SenseInfoBuffer

Miniport driver should ignore this member. 


### -field NextSrb

Miniport driver should ignore this member. 


### -field OriginalRequest

Miniport driver should ignore this member. 


### -field SrbExtension

A pointer to the SRB extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure. The Storport driver does not initialize the memory that this member points to. The HBA can directly access the data that the miniport driver writes into the SRB extension. A miniport driver can obtain the physical address of the SRB extension by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567095">StorPortGetPhysicalAddress</a> routine. 


### -field SrbPnPFlags

The PNP flags. Currently, the only flag allowed is SRB_PNP_FLAGS_ADAPTER_REQUEST, which indicates that the PNP request is for the adapter, and not for one of the devices on the adapter. If this flag is set, the miniport driver should ignore the values in the <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>.


### -field Reserved

Reserved for system use.


### -field Reserved4

Reserved for system use.


## -remarks



The Storport driver sends <b>SCSI_PNP_REQUEST_BLOCK</b> requests to a miniport driver to notify the miniport driver of Windows plug and play events that affect storage devices that are connected to the adapter.

The Storport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff557369">HwStorBuildIo</a> to pass SRBs to the miniport driver. <b>HwStorBuildIo</b> checks the <b>Function</b> member of the SRB to determine the type of the SRB. If the <b>Function</b> member is set to SRB_FUNCTION_PNP, the SRB is a structure of type <b>SCSI_PNP_REQUEST_BLOCK</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557369">HwStorBuildIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a>
 

 

