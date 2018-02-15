---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH
title: "_MPIO_PASS_THROUGH_PATH"
author: windows-driver-content
description: The MPIO_PASS_THROUGH_PATH structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path.htm
old-project: storage
ms.assetid: 8c7f3832-3faa-4ece-8434-338f1b150ec1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH, ntddscsi/MPIO_PASS_THROUGH_PATH, PMPIO_PASS_THROUGH_PATH structure pointer [Storage Devices], structs-scsibus_0a643059-71aa-4dca-92a8-525924a999df.xml, MPIO_PASS_THROUGH_PATH, _MPIO_PASS_THROUGH_PATH, MPIO_PASS_THROUGH_PATH structure [Storage Devices], storage.mpio_pass_through_path, ntddscsi/PMPIO_PASS_THROUGH_PATH, PMPIO_PASS_THROUGH_PATH"
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
-	MPIO_PASS_THROUGH_PATH
product: Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH, *PMPIO_PASS_THROUGH_PATH
---

# _MPIO_PASS_THROUGH_PATH structure


## -description


The <b>MPIO_PASS_THROUGH_PATH</b> structure is used together with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path.md">IOCTL_MPIO_PASS_THROUGH_PATH</a> request to instruct the port driver to send an embedded SCSI command to the target device. 


## -syntax


````
typedef struct _MPIO_PASS_THROUGH_PATH {
  SCSI_PASS_THROUGH PassThrough;
  ULONG             Version;
  USHORT            Length;
  UCHAR             Flags;
  UCHAR             PortNumber;
  ULONGLONG         MpioPathId;
} MPIO_PASS_THROUGH_PATH, *PMPIO_PASS_THROUGH_PATH;
````


## -struct-fields




### -field PassThrough

Contains a <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a> structure that is set up in the same way as it is for an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a> request.


### -field Version

Should be zero.


### -field Length

The size of the <b>MPIO_PASS_THROUGH_PATH</b> structure.


### -field Flags



###### 



########## 


### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a> structure.


### -field MpioPathId

The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.


## -remarks



The <b>MPIO_PASS_THROUGH_PATH</b> structure is used for a double-buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>. When the system handles an <b>IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</b> request, it locks down the buffer in user memory, and the device accesses this memory directly.




## -see-also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>



<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path.md">IOCTL_MPIO_PASS_THROUGH_PATH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MPIO_PASS_THROUGH_PATH structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

