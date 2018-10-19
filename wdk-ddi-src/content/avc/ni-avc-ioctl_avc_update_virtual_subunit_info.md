---
UID: NI:avc.IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO
title: IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO
author: windows-driver-content
description: The IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits.
old-location: stream\ioctl_avc_update_virtual_subunit_info.htm
tech.root: stream
ms.assetid: 2a66ea7f-bfa1-4c51-a93d-18043fc49066
ms.date: 04/23/2018
ms.keywords: IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO, IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO control, IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO control code [Streaming Media Devices], avc/IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO, avcref_70967704-87c3-4d0b-856f-e031ae0011cc.xml, stream.ioctl_avc_update_virtual_subunit_info
ms.topic: ioctl
req.header: avc.h
req.include-header: Avc.h
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
-	avc.h
api_name:
-	IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO IOCTL


## -description



The IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits. It is available to user mode as well as kernel-mode components through the IRP_MJ_DEVICE_CONTROL dispatch. For driver-to-driver communication, it is a METHOD_BUFFERED IOCTL, so set the IRP fields accordingly (IrpStack-&gt;Parameters.DeviceIoControl.InputBufferLength and Irp-&gt;AssociatedIrp.SystemBuffer).

IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO is used to add or remove subunit IDs of a single type. Successive calls with a different ID part of the subunit address cause the number of enumerated IDs to change. Note that <i>avc.sys</i> adds or removes the highest IDs only. This is a limitation of the AV/C specification, not the driver implementation.

This IOCTL uses the AVC_SUBUNIT_ADDR_SPEC structure.




## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If successful, the AV/C protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS.

Possible other return values include:

<table>
<tr>
<th>Return Value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_INSUFFICIENT_RESOURCES

</td>
<td>
No buffer was passed, or insufficient resources available to perform a registry query.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_BUFFER_SIZE

</td>
<td>
The buffer passed in Irp-&gt;AssociatedIrp.SystemBuffer must be at least as large as sizeof(AVC_SUBUNIT_ADDR_SPEC) which includes a single-byte subunit address, but limited to a 32 byte subunit address.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
The subunit address was specified incorrectly.

</td>
</tr>
<tr>
<td>
STATUS_ACCESS_DENIED

</td>
<td>
The current user has insufficient registry access privileges to make the update persistent.

</td>
</tr>
</table>
 


## -remarks



Must be called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554198">AVC_SUBUNIT_ADDR_SPEC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560783">IOCTL_AVC_BUS_RESET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560789">IOCTL_AVC_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560793">IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO</a>
 

 


