---
UID: NS:ntddscsi._ATA_PASS_THROUGH_DIRECT
title: "_ATA_PASS_THROUGH_DIRECT"
author: windows-driver-content
description: The ATA_PASS_THROUGH_DIRECT structure is used in conjunction with an IOCTL_ATA_PASS_THROUGH_DIRECT request to instruct the port driver to send an embedded ATA command to the target device.
old-location: storage\ata_pass_through_direct.htm
old-project: storage
ms.assetid: 0f7a424e-5d83-4ab0-b5a2-7e9093bbd34b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddscsi/PATA_PASS_THROUGH_DIRECT, ATA_PASS_THROUGH_DIRECT structure [Storage Devices], structs-IDE_e59bb754-2ad4-49d0-b68c-8ef7b6273af5.xml, ATA_PASS_THROUGH_DIRECT, *PATA_PASS_THROUGH_DIRECT, _ATA_PASS_THROUGH_DIRECT, PATA_PASS_THROUGH_DIRECT structure pointer [Storage Devices], ntddscsi/ATA_PASS_THROUGH_DIRECT, storage.ata_pass_through_direct, PATA_PASS_THROUGH_DIRECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddscsi.h
apiname:
-	ATA_PASS_THROUGH_DIRECT
product: Windows
targetos: Windows
req.typenames: "*PATA_PASS_THROUGH_DIRECT, ATA_PASS_THROUGH_DIRECT"
---

# _ATA_PASS_THROUGH_DIRECT structure


## -description


The ATA_PASS_THROUGH_DIRECT structure is used in conjunction with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through_direct.md">IOCTL_ATA_PASS_THROUGH_DIRECT</a> request to instruct the port driver to send an embedded ATA command to the target device. 


## -syntax


````
typedef struct _ATA_PASS_THROUGH_DIRECT {
  USHORT Length;
  USHORT AtaFlags;
  UCHAR  PathId;
  UCHAR  TargetId;
  UCHAR  Lun;
  UCHAR  ReservedAsUchar;
  ULONG  DataTransferLength;
  ULONG  TimeOutValue;
  ULONG  ReservedAsUlong;
  PVOID  DataBuffer;
  UCHAR  PreviousTaskFile[8];
  UCHAR  CurrentTaskFile[8];
} ATA_PASS_THROUGH_DIRECT, *PATA_PASS_THROUGH_DIRECT;
````


## -struct-fields




#### - Length

Specifies the length in bytes of the ATA_PASS_THROUGH_DIRECT structure.


#### - AtaFlags

Indicates the direction of data transfer and specifies the kind of operation to be performed. The value of this member must be some combination of the flags in the following table.
<table>
<tr>
<th>ATA flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ATA_FLAGS_DRDY_REQUIRED

</td>
<td>
Wait for DRDY status from the device before sending the command to the device.

</td>
</tr>
<tr>
<td>
ATA_FLAGS_DATA_IN

</td>
<td>
Read data from the device.

</td>
</tr>
<tr>
<td>
ATA_FLAGS_DATA_OUT

</td>
<td>
Write data to the device.

</td>
</tr>
<tr>
<td>
ATA_FLAGS_48BIT_COMMAND

</td>
<td>
The ATA command to be sent uses the 48-bit logical block address (LBA) feature set. When this flag is set, the contents of the <b>PreviousTaskFile</b> member in the ATA_PASS_THROUGH_DIRECT structure should be valid.

</td>
</tr>
<tr>
<td>
ATA_FLAGS_USE_DMA

</td>
<td>
Set the transfer mode to DMA.

</td>
</tr>
<tr>
<td>
ATA_FLAGS_NO_MULTIPLE

</td>
<td>
Read single sector only.

</td>
</tr>
</table> 


#### - PathId

Contains an integer that indicates the IDE port or bus for the request. This value is set by the port driver.


#### - TargetId

Contains an integer that indicates the target device on the bus. This value is set by the port driver.


#### - Lun

Indicates the logical unit number of the device. This value is set by the port driver.


#### - ReservedAsUchar

Reserved for future use. 


#### - DataTransferLength

Indicates the size, in bytes, of the data buffer. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. 


#### - TimeOutValue

Indicates the number of seconds that are allowed for the request to execute before the OS-specific port driver determines that the request has timed out.


#### - ReservedAsUlong

Reserved for future use.


#### - DataBuffer

Pointer to the data buffer.


#### - PreviousTaskFile

Specifies the contents of the input task file register prior to the current pass-through command. This member is not used when the ATA_FLAGS_48BIT_COMMAND flag is not set. 


#### - CurrentTaskFile

Specifies the content of the task file register on both input and output. On input, the array values in <b>CurrentTaskFile</b> map to the input registers in the following manner.
<table>
<tr>
<th>Byte</th>
<th>Input Register</th>
</tr>
<tr>
<td>
0

</td>
<td>
Features Register

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Sector Count Register

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Sector Number Register

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Cylinder Low Register

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Cylinder High Register

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Device/Head Register

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Command Register

</td>
</tr>
<tr>
<td>
7

</td>
<td>
Reserved

</td>
</tr>
</table> 

When <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through_direct.md">IOCTL_ATA_PASS_THROUGH_DIRECT</a> completes, the port driver updates <b>CurrentTaskFile</b> with the values that are present in the device's output registers at the completion of the embedded command. The array values in <b>CurrentTaskFile</b> correspond to the following task file output registers.
<table>
<tr>
<th>Byte</th>
<th>Output Register</th>
</tr>
<tr>
<td>
0

</td>
<td>
Error Register

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Sector Count Register

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Sector Number Register

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Cylinder Low Register

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Cylinder High Register

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Device/Head Register

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Status Register

</td>
</tr>
<tr>
<td>
7

</td>
<td>
Reserved

</td>
</tr>
</table> 


## -remarks


The ATA_PASS_THROUGH_DIRECT structure is used with <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through_direct.md">IOCTL_ATA_PASS_THROUGH_DIRECT</a>. With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request, see <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a> and <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_ex.md">ATA_PASS_THROUGH_EX</a>.



## -see-also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a>

<a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_ex.md">ATA_PASS_THROUGH_EX</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through_direct.md">IOCTL_ATA_PASS_THROUGH_DIRECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ATA_PASS_THROUGH_DIRECT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

