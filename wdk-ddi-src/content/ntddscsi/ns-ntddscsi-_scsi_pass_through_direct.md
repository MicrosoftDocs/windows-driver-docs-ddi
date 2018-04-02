---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_DIRECT
title: "_SCSI_PASS_THROUGH_DIRECT"
author: windows-driver-content
description: The SCSI_PASS_THROUGH_DIRECT structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct.htm
old-project: storage
ms.assetid: 306babe7-393f-4b4a-9d8a-4c973cb3eaa2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSCSI_PASS_THROUGH_DIRECT, PSCSI_PASS_THROUGH_DIRECT, PSCSI_PASS_THROUGH_DIRECT structure pointer [Storage Devices], SCSI_PASS_THROUGH_DIRECT, SCSI_PASS_THROUGH_DIRECT structure [Storage Devices], _SCSI_PASS_THROUGH_DIRECT, ntddscsi/PSCSI_PASS_THROUGH_DIRECT, ntddscsi/SCSI_PASS_THROUGH_DIRECT, storage.scsi_pass_through_direct, structs-scsibus_64c46eef-e5bc-4e81-a479-2bdbd93605e7.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddscsi.h
api_name:
-	SCSI_PASS_THROUGH_DIRECT
product:
- Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_DIRECT, *PSCSI_PASS_THROUGH_DIRECT
---

# _SCSI_PASS_THROUGH_DIRECT structure


## -description


The <b>SCSI_PASS_THROUGH_DIRECT</b> structure is used in conjunction with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> request to instruct the port driver to send an embedded SCSI command to the target device. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

Contains the value of <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT).  


### -field ScsiStatus

Reports the SCSI status that was returned by the HBA or the target device. 


### -field PathId

Indicates the SCSI port or bus for the request. 


### -field TargetId

Indicates the target controller or device on the bus.  


### -field Lun

Indicates the logical unit number of the device. 


### -field CdbLength

Indicates the size in bytes of the SCSI command descriptor block. 


### -field SenseInfoLength

Indicates the size in bytes of the request-sense buffer. 


### -field DataIn



#####  This field must have one of three values:



####### 


### -field DataTransferLength

Indicates the size in bytes of the data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.


### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out.


### -field DataBuffer

Pointer to the data buffer. 


### -field SenseInfoOffset

Contains an offset from the beginning of this structure to the request-sense buffer. 


### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device. 


## -remarks



The SCSI_PASS_THROUGH_DIRECT structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>. With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a>.

The members of SCSI_PASS_THROUGH_DIRECT correspond roughly to the members of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> structure. The values of the <b>DataIn</b> member correspond to the SCSI_IOCTL_DATA_IN, SCSI_IOCTL_DATA_OUT, and SCSI_IOCTL_DATA_UNSPECIFIED flags assigned to <b>SrbFlags</b> member of SCSI_REQUEST_BLOCK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
 

 

