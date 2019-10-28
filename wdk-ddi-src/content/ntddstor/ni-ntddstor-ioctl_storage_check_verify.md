---
UID: NI:ntddstor.IOCTL_STORAGE_CHECK_VERIFY
title: IOCTL_STORAGE_CHECK_VERIFY (ntddstor.h)
description: Determines whether the media has changed on a removable-media device that the caller has opened for read or write access.
old-location: storage\ioctl_storage_check_verify.htm
tech.root: storage
ms.assetid: 12e98642-2ed5-47d6-9461-9d6c52149749
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_CHECK_VERIFY, IOCTL_STORAGE_CHECK_VERIFY control, IOCTL_STORAGE_CHECK_VERIFY control code [Storage Devices], k307_5ec9ef19-a741-4fb9-876e-7cfc35699dbe.xml, ntddstor/IOCTL_STORAGE_CHECK_VERIFY, storage.ioctl_storage_check_verify
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_CHECK_VERIFY"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- Ntddstor.h
api_name:
- IOCTL_STORAGE_CHECK_VERIFY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_CHECK_VERIFY IOCTL


## -description



Determines whether the media has changed on a removable-media device that the caller has opened for read or write access. If read or write access to the device is not necessary, the caller can improve performance by opening the device with FILE_READ_ATTRIBUTES and issuing an<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_check_verify2">IOCTL_STORAGE_CHECK_VERIFY2</a> request instead. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/supporting-removable-media">Supporting Removable Media</a>.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

Optionally, for disk and CD-ROM devices, <b>Irp->AssociatedIrp.SystemBuffer</b> points to a buffer to receive the media change count. The driver fills this buffer only if <b>Parameters.DeviceIoControl.OutputBufferLength</b> was nonzero and the return value is STATUS_SUCCESS. The media change count is a ULONG indicating how many times the media has changed since the driver started.

Otherwise, this request has no output.


### -output-buffer-length

Optionally, for disk and CD-ROM devices, <b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of a buffer, which must be >= <b>sizeof</b>(ULONG). This field is zero if the optional buffer is not specified.

Otherwise, this request has no input.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If a disk or CD-ROM driver has no indication that the media has changed, the driver sets the <b>Status</b> field to STATUS_SUCCESS. In addition, if the optional media change buffer was specified, the driver returns the media change count in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> and sets the <b>Information</b> field to <b>sizeof</b>(ULONG). If the optional media change buffer was not specified, the driver sets <b>Information</b> to zero.

If the driver detects that the media has changed and the volume is mounted (VPB_MOUNTED is set in the VPB), it must: 

<ol>
<li>
Set <b>Information</b> to zero.

</li>
<li>
Set <b>Status</b> to STATUS_VERIFY_REQUIRED.

</li>
<li>
Set the DO_VERIFY_VOLUME flag in the <b>DeviceObject.</b>

</li>
<li>
Call <b>IoCompleteRequest</b> with the input IRP.

</li>
</ol>
If the driver detects that the media has changed, but the volume is not mounted, the driver must not set the DO_VERIFY_VOLUME bit. Instead, it should do the following:

<ol>
<li>
Set <b>Status</b> to STATUS_IO_DEVICE_ERROR.

</li>
<li>
Set <b>Information</b> to zero.

</li>
<li>
Call <b>IoCompleteRequest</b> with the IRP.

</li>
</ol>
If the driver detects an error such as STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, or a device error, it sets <b>Information</b> to zero and sets the appropriate error value in the <b>Status</b> field. 

For a tape driver, the <b>Information</b> field is set to zero and the <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_check_verify2">IOCTL_STORAGE_CHECK_VERIFY2</a>
 

 

