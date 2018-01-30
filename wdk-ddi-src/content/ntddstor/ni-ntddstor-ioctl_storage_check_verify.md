---
UID: NI:ntddstor.IOCTL_STORAGE_CHECK_VERIFY
title: IOCTL_STORAGE_CHECK_VERIFY
author: windows-driver-content
description: Determines whether the media has changed on a removable-media device that the caller has opened for read or write access.
old-location: storage\ioctl_storage_check_verify.htm
old-project: storage
ms.assetid: 12e98642-2ed5-47d6-9461-9d6c52149749
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_check_verify, IOCTL_STORAGE_CHECK_VERIFY control code [Storage Devices], IOCTL_STORAGE_CHECK_VERIFY, ntddstor/IOCTL_STORAGE_CHECK_VERIFY, k307_5ec9ef19-a741-4fb9-876e-7cfc35699dbe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_CHECK_VERIFY
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_CHECK_VERIFY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Determines whether the media has changed on a removable-media device that the caller has opened for read or write access. If read or write access to the device is not necessary, the caller can improve performance by opening the device with FILE_READ_ATTRIBUTES and issuing an<a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify2.md">IOCTL_STORAGE_CHECK_VERIFY2</a> request instead. 

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

Optionally, for disk and CD-ROM devices, <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer to receive the media change count. The driver fills this buffer only if <b>Parameters.DeviceIoControl.OutputBufferLength</b> was nonzero and the return value is STATUS_SUCCESS. The media change count is a ULONG indicating how many times the media has changed since the driver started.

Otherwise, this request has no output.


### -output-buffer-length

Optionally, for disk and CD-ROM devices, <b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of a buffer, which must be &gt;= <b>sizeof</b>(ULONG). This field is zero if the optional buffer is not specified.

Otherwise, this request has no input.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If a disk or CD-ROM driver has no indication that the media has changed, the driver sets the <b>Status</b> field to STATUS_SUCCESS. In addition, if the optional media change buffer was specified, the driver returns the media change count in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> and sets the <b>Information</b> field to <b>sizeof</b>(ULONG). If the optional media change buffer was not specified, the driver sets <b>Information</b> to zero.

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
</ol>If the driver detects that the media has changed, but the volume is not mounted, the driver must not set the DO_VERIFY_VOLUME bit. Instead, it should do the following:
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
</ol>If the driver detects an error such as STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, or a device error, it sets <b>Information</b> to zero and sets the appropriate error value in the <b>Status</b> field. 

For a tape driver, the <b>Information</b> field is set to zero and the <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_VERIFY_REQUIRED.


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify2.md">IOCTL_STORAGE_CHECK_VERIFY2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_CHECK_VERIFY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

