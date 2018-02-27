---
UID: NI:ntddtape.IOCTL_TAPE_GET_STATUS
title: IOCTL_TAPE_GET_STATUS
author: windows-driver-content
description: Returns the current status of the drive in the Status field of the I/O status block.
old-location: storage\ioctl_tape_get_status.htm
old-project: storage
ms.assetid: d5e491b8-d40c-4f2c-9117-5c3cb71913f7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_TAPE_GET_STATUS, IOCTL_TAPE_GET_STATUS control code [Storage Devices], k307_8ab90364-adac-4937-9036-aa28ddeffb19.xml, ntddtape/IOCTL_TAPE_GET_STATUS, storage.ioctl_tape_get_status
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
-	Ntddtape.h
apiname:
-	IOCTL_TAPE_GET_STATUS
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_GET_STATUS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns the current status of the drive in the <b>Status</b> field of the I/O status block. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to one of the following NT status values: 

<ul>
<li>
STATUS_SUCCESS

</li>
<li>
STATUS_INSUFFICIENT_RESOURCES

</li>
<li>
STATUS_NOT_IMPLEMENTED

</li>
<li>
STATUS_INVALID_DEVICE_REQUEST

</li>
<li>
STATUS_INVALID_PARAMETER

</li>
<li>
STATUS_VERIFY_REQUIRED

</li>
<li>
STATUS_BUS_RESET

</li>
<li>
STATUS_SETMARK_DETECTED

</li>
<li>
STATUS_FILEMARK_DETECTED

</li>
<li>
STATUS_BEGINNING_OF_MEDIA

</li>
<li>
STATUS_END_OF_MEDIA

</li>
<li>
STATUS_BUFFER_OVERFLOW

</li>
<li>
STATUS_NO_DATA_DETECTED

</li>
<li>
STATUS_EOM_OVERFLOW

</li>
<li>
STATUS_NO_MEDIA

</li>
<li>
STATUS_IO_DEVICE_ERROR

</li>
<li>
STATUS_UNRECOGNIZED_MEDIA

</li>
<li>
STATUS_DEVICE_NOT_READY

</li>
<li>
STATUS_MEDIA_WRITE_PROTECTED

</li>
<li>
STATUS_DEVICE_DATA_ERROR

</li>
<li>
STATUS_NO_SUCH_DEVICE

</li>
<li>
STATUS_INVALID_BLOCK_LENGTH

</li>
<li>
STATUS_IO_TIMEOUT

</li>
<li>
STATUS_DEVICE_NOT_CONNECTED

</li>
<li>
STATUS_DATA_OVERRUN

</li>
<li>
STATUS_DEVICE_BUSY

</li>
<li>
STATUS_DEVICE_REQUIRES_CLEANING

</li>
<li>
STATUS_CLEANER_CARTRIDGE_INSTALLED

</li>
</ul>
Each of these NT status values correspond to a value in the <a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a> enumerator. For more information about the significance of these values and a mapping between the NT status values and the TAPE_STATUS values, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>.


## -see-also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_GET_STATUS control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

