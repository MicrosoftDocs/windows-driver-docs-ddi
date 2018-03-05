---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH_EX
title: "_MPIO_PASS_THROUGH_PATH_EX"
author: windows-driver-content
description: The MPIO_PASS_THROUGH_PATH_EX structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path_ex.htm
old-project: storage
ms.assetid: DAEA7A9C-3ACD-49E5-A634-A844D9694412
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH_EX, MPIO_PASS_THROUGH_PATH_EX, MPIO_PASS_THROUGH_PATH_EX structure [Storage Devices], PMPIO_PASS_THROUGH_PATH_EX, PMPIO_PASS_THROUGH_PATH_EX structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH_EX, ntddscsi/MPIO_PASS_THROUGH_PATH_EX, ntddscsi/PMPIO_PASS_THROUGH_PATH_EX, storage.mpio_pass_through_path_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	MPIO_PASS_THROUGH_PATH_EX
product: Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH_EX, *PMPIO_PASS_THROUGH_PATH_EX
---

# _MPIO_PASS_THROUGH_PATH_EX structure


## -description


The <b>MPIO_PASS_THROUGH_PATH_EX</b>  structure is used together with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_ex.md">IOCTL_MPIO_PASS_THROUGH_PATH_EX</a> request to instruct the port driver to send an embedded SCSI command to the target device.


## -syntax


````
typedef struct _MPIO_PASS_THROUGH_PATH_EX {
  ULONG     PassThroughOffset;
  ULONG     Version;
  USHORT    Length;
  UCHAR     Flags;
  UCHAR     PortNumber;
  ULONGLONG MpioPathId;
} MPIO_PASS_THROUGH_PATH_EX, *PMPIO_PASS_THROUGH_PATH_EX;
````


## -struct-fields




### -field PassThroughOffset

The offset from the beginning of this structure to a <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> structure that is configured in the same manner as it is for an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a> request.


### -field Version

Should be zero.


### -field Length

The size of the <b>MPIO_PASS_THROUGH_PATH_EX</b> structure.


### -field Flags



###### 



########## 


### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathID</b> and <b>TargetId</b> values are taken from address structure associated with the embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a> structure.


### -field MpioPathId

The <b>PathID</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.


## -remarks



<div class="alert"><b>Note</b>  All 32 bit processes running on a 64 bit version of Windows must use the <b>MPIO_PASS_THROUGH_PATH32_EX</b> structure when issuing an <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_ex.md">IOCTL_MPIO_PASS_THROUGH_PATH_EX</a> request.</div>
<div> </div>



## -see-also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a>



<a href="..\minitape\ns-minitape-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct_ex.md">SCSI_PASS_THROUGH_DIRECT_EX</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct_ex.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_ex.md">IOCTL_MPIO_PASS_THROUGH_PATH_EX</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MPIO_PASS_THROUGH_PATH_EX structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

