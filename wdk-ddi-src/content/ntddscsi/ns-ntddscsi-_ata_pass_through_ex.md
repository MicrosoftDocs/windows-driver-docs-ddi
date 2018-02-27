---
UID: NS:ntddscsi._ATA_PASS_THROUGH_EX
title: "_ATA_PASS_THROUGH_EX"
author: windows-driver-content
description: The ATA_PASS_THROUGH_EX structure is used in conjunction with an IOCTL_ATA_PASS_THROUGH request to instruct the port driver to send an embedded ATA command to the target device.
old-location: storage\ata_pass_through_ex.htm
old-project: storage
ms.assetid: 76d8f5be-0011-4a7c-ac21-7115ad7e1155
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PATA_PASS_THROUGH_EX, ATA_PASS_THROUGH_EX, ATA_PASS_THROUGH_EX structure [Storage Devices], PATA_PASS_THROUGH_EX, PATA_PASS_THROUGH_EX structure pointer [Storage Devices], _ATA_PASS_THROUGH_EX, ntddscsi/ATA_PASS_THROUGH_EX, ntddscsi/PATA_PASS_THROUGH_EX, storage.ata_pass_through_ex, structs-IDE_72cc1a49-a438-40cb-b4b5-8ec7c87669f8.xml"
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
-	ATA_PASS_THROUGH_EX
product: Windows
targetos: Windows
req.typenames: ATA_PASS_THROUGH_EX, *PATA_PASS_THROUGH_EX
---

# _ATA_PASS_THROUGH_EX structure


## -description


The ATA_PASS_THROUGH_EX structure is used in conjunction with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a> request to instruct the port driver to send an embedded ATA command to the target device. 


## -syntax


````
typedef struct _ATA_PASS_THROUGH_EX {
  USHORT    Length;
  USHORT    AtaFlags;
  UCHAR     PathId;
  UCHAR     TargetId;
  UCHAR     Lun;
  UCHAR     ReservedAsUchar;
  ULONG     DataTransferLength;
  ULONG     TimeOutValue;
  ULONG     ReservedAsUlong;
  ULONG_PTR DataBufferOffset;
  UCHAR     PreviousTaskFile[8];
  UCHAR     CurrentTaskFile[8];
} ATA_PASS_THROUGH_EX, *PATA_PASS_THROUGH_EX;
````


## -struct-fields




### -field Length

Specifies the length in bytes of the ATA_PASS_THROUGH_EX structure.


### -field AtaFlags

Indicates the direction of data transfer and specifies the kind of operation to be performed. The value of this member must be some combination of the following flags:

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
The ATA command to be sent uses the 48-bit logical block address (LBA) feature set. When this flag is set, the contents of the <b>PreviousTaskFile</b> member in the ATA_PASS_THROUGH_EX structure should be valid.

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
 


### -field PathId

Contains an integer that indicates the IDE port or bus for the request. This value is set by the port driver.


### -field TargetId

Contains an integer that indicates the target device on the bus. This value is set by the port driver.


### -field Lun

Indicates the logical unit number of the device. This value is set by the port driver.


### -field ReservedAsUchar

Reserved for future use. 


### -field DataTransferLength

Indicates the size, in bytes, of the data buffer. If an underrun occurs, the miniport driver must update this member to the number of bytes that were actually transferred. 


### -field TimeOutValue

Indicates the number of seconds that are allowed for the request to execute before the OS-specific port driver determines that the request has timed out. 


### -field ReservedAsUlong

Reserved for future use. 


### -field DataBufferOffset

Specifies the offset, in bytes, from the beginning of this structure to the data buffer. 


### -field PreviousTaskFile

Specifies the contents of the task file input registers prior to the current pass-through command. This member is not used when the ATA_FLAGS_48BIT_COMMAND flag is not set. 


### -field CurrentTaskFile

Specifies the content of the task file register on both input and output. On input, the array values in <b>CurrentTaskFile</b> map to the task file input registers in the following manner.

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
Features register

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Sector count register

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Sector number register

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Cylinder low register

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Cylinder high register

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Device/head register

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Command register

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
 

When <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a> completes, the port driver updates <b>CurrentTaskFile</b> with the values that are present in the device's output registers at the completion of the embedded command. The array values in <b>CurrentTaskFile</b> correspond to the following task file output registers.

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
Error register

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Sector count register

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Sector number register

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Cylinder low register

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Cylinder high register

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Device/head register

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Status register

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




<a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a> is a buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through_direct.md">IOCTL_ATA_PASS_THROUGH_DIRECT</a> and <a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a>. When handling an IOCTL_ATA_PASS_THROUGH_DIRECT request, the system locks down the buffer in user memory and the device accesses this memory directly. 




## -see-also

<a href="..\ntddscsi\ns-ntddscsi-_ata_pass_through_direct.md">ATA_PASS_THROUGH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through.md">IOCTL_ATA_PASS_THROUGH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_ata_pass_through_direct.md">IOCTL_ATA_PASS_THROUGH_DIRECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ATA_PASS_THROUGH_EX structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

