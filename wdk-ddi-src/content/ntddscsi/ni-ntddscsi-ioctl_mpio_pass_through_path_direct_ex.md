---
UID: NI:ntddscsi.IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX
title: IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX (ntddscsi.h)
description: The IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX control code request is the extended version of the IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT request. This request provides support for bidirectional data transfers and allows a command data block (CDB) > 16 bytes.
old-location: storage\ioctl_mpio_pass_through_path_direct_ex.htm
tech.root: storage
ms.assetid: 2B5AF281-C080-4ED9-9C58-5757CDE0117A
ms.date: 03/29/2018
keywords: ["IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX IOCTL"]
ms.keywords: IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX, IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX control, IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX control code [Storage Devices], ntddscsi/IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX, storage.ioctl_mpio_pass_through_path_direct_ex
f1_keywords:
 - "ntddscsi/IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX"
 - "IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddscsi.h
api_name:
- IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX IOCTL


## -description


The <b>IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</b> control code request 
     is the extended version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_mpio_pass_through_path_direct">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a> request. This request provides support for bidirectional data transfers and allows a command data block (CDB) > 16 bytes.

This I/O control code allows an application or kernel driver to send a SCSI command to a designated real LUN. The following restrictions apply to the use of this I/O control code:
<ul>
<li>
If a class driver for the pseudo LUN exists, the application must send the request to that class driver. Thus, an application can send this request directly to an MPIO only if there is no class driver for the device.

</li>
<li>
All pass-through requests must be synchronous.

</li>
<li>
Applications do not require administrative privileges to send a pass-through request to a device, but they must have read/write access to the device.

</li>
<li>
The request comprises a SCSI pass-through request (in an embedded <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a> structure) as well as certain directives.

</li>
<li>
The SCSI pass-through structure should meet the requirements for such, as described in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct">SCSI_PASS_THROUGH_DIRECT</a>.

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

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length

The buffer must be at least <b>sizeof</b>(MPIO_PASS_THROUGH_PATH_DIRECT_EX) or, if sent by a 32-bit application in a 64-bit operating system, <b>sizeof</b>(MPIO_PASS_THROUGH_PATH_DIRECT32_EX).


### -output-buffer

The port driver returns any request-sense data and any data that is transferred from the device to the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

The <b>SenseInfoLength</b> and <b>DataOutTransferLength</b> in the embedded <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct_ex">SCSI_PASS_THROUGH_DIRECT_EX</a> structure are updated to indicate the amount of data that is transferred.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned in the output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in the embedded <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct_ex">SCSI_PASS_THROUGH_DIRECT_EX</a> is improperly set.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_mpio_pass_through_path_direct_ex">MPIO_PASS_THROUGH_PATH_DIRECT_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct_ex">SCSI_PASS_THROUGH_DIRECT_EX</a>
 

 

