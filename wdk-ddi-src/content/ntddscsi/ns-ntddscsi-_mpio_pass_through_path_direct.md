---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH_DIRECT
title: "_MPIO_PASS_THROUGH_PATH_DIRECT"
author: windows-driver-content
description: The MPIO_PASS_THROUGH_PATH_DIRECT structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path_direct.htm
old-project: storage
ms.assetid: b4ddaee3-97af-46a6-982c-16b5f6966a08
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH_DIRECT, MPIO_PASS_THROUGH_PATH_DIRECT, MPIO_PASS_THROUGH_PATH_DIRECT structure [Storage Devices], PMPIO_PASS_THROUGH_PATH_DIRECT, PMPIO_PASS_THROUGH_PATH_DIRECT structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH_DIRECT, ntddscsi/MPIO_PASS_THROUGH_PATH_DIRECT, ntddscsi/PMPIO_PASS_THROUGH_PATH_DIRECT, storage.mpio_pass_through_path_direct, structs-scsibus_54825e13-2114-46d8-ab0f-84feb86b8f5c.xml"
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
-	MPIO_PASS_THROUGH_PATH_DIRECT
product: Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH_DIRECT, *PMPIO_PASS_THROUGH_PATH_DIRECT
---

# _MPIO_PASS_THROUGH_PATH_DIRECT structure


## -description


The <b>MPIO_PASS_THROUGH_PATH_DIRECT</b> structure is used together with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a> request to instruct the port driver to send an embedded SCSI command to the target device. 


## -syntax


````
typedef struct _MPIO_PASS_THROUGH_PATH_DIRECT {
  SCSI_PASS_THROUGH_DIRECT PassThrough;
  ULONG                    Version;
  USHORT                   Length;
  UCHAR                    Flags;
  UCHAR                    PortNumber;
  ULONGLONG                MpioPathId;
} MPIO_PASS_THROUGH_PATH_DIRECT, *PMPIO_PASS_THROUGH_PATH_DIRECT;
````


## -struct-fields




### -field PassThrough

Contains a <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a> structure that is set up in the same way as it is for an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> request.


### -field Version

Should be zero.


### -field Length

The size of the <b>MPIO_PASS_THROUGH_PATH_DIRECT</b> structure.


### -field Flags



###### 



########## 


### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a> structure.


### -field MpioPathId

The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.


## -remarks



The <b>MPIO_PASS_THROUGH_PATH_DIRECT</b> structure is used for a single-buffered device control request. To use double-buffering, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path.md">IOCTL_MPIO_PASS_THROUGH_PATH</a>.




## -see-also

<a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path.md">IOCTL_MPIO_PASS_THROUGH_PATH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



 

 


