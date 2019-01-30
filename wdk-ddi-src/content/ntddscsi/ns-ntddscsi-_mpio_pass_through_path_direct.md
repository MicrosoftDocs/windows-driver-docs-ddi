---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH_DIRECT
title: _MPIO_PASS_THROUGH_PATH_DIRECT (ntddscsi.h)
description: The MPIO_PASS_THROUGH_PATH_DIRECT structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path_direct.htm
tech.root: storage
ms.assetid: b4ddaee3-97af-46a6-982c-16b5f6966a08
ms.date: 03/29/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH_DIRECT, MPIO_PASS_THROUGH_PATH_DIRECT, MPIO_PASS_THROUGH_PATH_DIRECT structure [Storage Devices], PMPIO_PASS_THROUGH_PATH_DIRECT, PMPIO_PASS_THROUGH_PATH_DIRECT structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH_DIRECT, ntddscsi/MPIO_PASS_THROUGH_PATH_DIRECT, ntddscsi/PMPIO_PASS_THROUGH_PATH_DIRECT, storage.mpio_pass_through_path_direct, structs-scsibus_54825e13-2114-46d8-ab0f-84feb86b8f5c.xml"
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
-	MPIO_PASS_THROUGH_PATH_DIRECT
product:
- Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH_DIRECT, *PMPIO_PASS_THROUGH_PATH_DIRECT
---

# _MPIO_PASS_THROUGH_PATH_DIRECT structure


## -description


The <b>MPIO_PASS_THROUGH_PATH_DIRECT</b> structure is used together with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560495">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a> request to instruct the port driver to send an embedded SCSI command to the target device. 


## -struct-fields




### -field PassThrough

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a> structure that is set up in the same way as it is for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> request.


### -field Version

Should be zero.


### -field Length

The size of the <b>MPIO_PASS_THROUGH_PATH_DIRECT</b> structure.


### -field Flags



###### 



########## 


### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a> structure.


### -field MpioPathId

The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.


## -remarks



The <b>MPIO_PASS_THROUGH_PATH_DIRECT</b> structure is used for a single-buffered device control request. To use double-buffering, callers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff560492">IOCTL_MPIO_PASS_THROUGH_PATH</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560492">IOCTL_MPIO_PASS_THROUGH_PATH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560495">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
 

 

