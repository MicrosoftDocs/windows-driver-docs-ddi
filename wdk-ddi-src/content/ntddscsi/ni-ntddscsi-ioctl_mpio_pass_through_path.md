---
UID: NI:ntddscsi.IOCTL_MPIO_PASS_THROUGH_PATH
title: IOCTL_MPIO_PASS_THROUGH_PATH
author: windows-driver-content
description: This I/O control code allows an application or kernel driver to send a SCSI command to a designated real LUN.
old-location: storage\ioctl_mpio_pass_through_path.htm
old-project: storage
ms.assetid: c87b9be3-05cf-4321-9ffc-16b319c9e179
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_MPIO_PASS_THROUGH_PATH, IOCTL_MPIO_PASS_THROUGH_PATH control code [Storage Devices], k307_3498bdee-456f-4924-b5f3-c80366d54c02.xml, ntddscsi/IOCTL_MPIO_PASS_THROUGH_PATH, storage.ioctl_mpio_pass_through_path
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	Ntddscsi.h
api_name:
-	IOCTL_MPIO_PASS_THROUGH_PATH
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_MPIO_PASS_THROUGH_PATH IOCTL


## -description



This I/O control code allows an application or kernel driver to send a SCSI command to a designated real LUN. The following restrictions apply to the use of this I/O control code:

<ul>
<li>
If a class driver for the pseudo LUN exists, the application must send the request to that class driver. Thus, an application can send this request directly to MPIO only if there is no class driver for the device.

</li>
<li>
All pass-through requests must be synchronous.

</li>
<li>
Applications do not require administrative privileges to send a pass-through request to a device, but they must have read/write access to the device.

</li>
<li>
The request comprises a SCSI pass-through request (in an embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a> structure) as well as certain directives.

</li>
<li>
The SCSI pass-through structure should meet the requirements for such, as described in <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a>.

</li>
<li>
If the request is to be sent through the DSM that claimed the real LUN, that must be indicated. In such a case, the DSM itself must indicate the same real LUN. Otherwise, the request will fail.

</li>
<li>
The request must specify the real LUN that is comprised by the pseudo LUN in terms of the former's SCSI address or its MPIO <b>PathId</b>, but not both.

</li>
</ul>



## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length

The buffer must be at least <b>sizeof</b>(MPIO_PASS_THROUGH_PATH) or, if sent by a 32-bit application in a 64-bit operating system, <b>sizeof</b>(MPIO_PASS_THROUGH_PATH32).


### -output-buffer

The port driver returns any request-sense data and any data that is transferred from the device to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

The <b>SenseInfoLength</b> and <b>DataTransferLength</b> members in the embedded SCSI_PASS_THROUGH structure are updated to indicate the amount of data that is transferred.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in the embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a> is improperly set.


## -see-also

<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a>



 

 


