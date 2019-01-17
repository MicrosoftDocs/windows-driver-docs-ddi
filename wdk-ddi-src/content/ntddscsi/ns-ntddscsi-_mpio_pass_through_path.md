---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH
title: "_MPIO_PASS_THROUGH_PATH"
description: The MPIO_PASS_THROUGH_PATH structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path.htm
tech.root: storage
ms.assetid: 8c7f3832-3faa-4ece-8434-338f1b150ec1
ms.date: 03/29/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH, MPIO_PASS_THROUGH_PATH, MPIO_PASS_THROUGH_PATH structure [Storage Devices], PMPIO_PASS_THROUGH_PATH, PMPIO_PASS_THROUGH_PATH structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH, ntddscsi/MPIO_PASS_THROUGH_PATH, ntddscsi/PMPIO_PASS_THROUGH_PATH, storage.mpio_pass_through_path, structs-scsibus_0a643059-71aa-4dca-92a8-525924a999df.xml"
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
-	MPIO_PASS_THROUGH_PATH
product:
- Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH, *PMPIO_PASS_THROUGH_PATH
---

# _MPIO_PASS_THROUGH_PATH structure


## -description


The <b>MPIO_PASS_THROUGH_PATH</b> structure is used together with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560492">IOCTL_MPIO_PASS_THROUGH_PATH</a> request to instruct the port driver to send an embedded SCSI command to the target device. 


## -struct-fields




### -field PassThrough

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a> structure that is set up in the same way as it is for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a> request.


### -field Version

Should be zero.


### -field Length

The size of the <b>MPIO_PASS_THROUGH_PATH</b> structure.


### -field Flags



###### 



########## 


### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a> structure.


### -field MpioPathId

The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.


## -remarks



The <b>MPIO_PASS_THROUGH_PATH</b> structure is used for a double-buffered device control request. To bypass buffering in system memory, callers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff560495">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>. When the system handles an <b>IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</b> request, it locks down the buffer in user memory, and the device accesses this memory directly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560492">IOCTL_MPIO_PASS_THROUGH_PATH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560495">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
 

 

