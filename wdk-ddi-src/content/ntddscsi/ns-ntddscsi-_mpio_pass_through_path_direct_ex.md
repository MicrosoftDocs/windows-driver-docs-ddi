---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH_DIRECT_EX
title: _MPIO_PASS_THROUGH_PATH_DIRECT_EX (ntddscsi.h)
description: The MPIO_PASS_THROUGH_PATH_DIRECT_EX structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path_direct_ex.htm
tech.root: storage
ms.assetid: 3EB8721D-291E-492A-9BB3-28F411195DD5
ms.date: 03/29/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH_DIRECT_EX, MPIO_PASS_THROUGH_PATH_DIRECT_EX, MPIO_PASS_THROUGH_PATH_DIRECT_EX structure [Storage Devices], PMPIO_PASS_THROUGH_PATH_DIRECT_EX, PMPIO_PASS_THROUGH_PATH_DIRECT_EX structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH_DIRECT_EX, ntddscsi/MPIO_PASS_THROUGH_PATH_DIRECT_EX, ntddscsi/PMPIO_PASS_THROUGH_PATH_DIRECT_EX, storage.mpio_pass_through_path_direct_ex"
f1_keywords:
 - "ntddscsi/MPIO_PASS_THROUGH_PATH_DIRECT_EX"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddscsi.h
api_name:
- MPIO_PASS_THROUGH_PATH_DIRECT_EX
product:
- Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH_DIRECT_EX, *PMPIO_PASS_THROUGH_PATH_DIRECT_EX
---

# _MPIO_PASS_THROUGH_PATH_DIRECT_EX structure


## -description


The <b>MPIO_PASS_THROUGH_PATH_DIRECT_EX</b> structure is used together with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_mpio_pass_through_path_direct_ex">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</a> request to instruct the port driver to send an embedded SCSI command to the target device.


## -struct-fields




### -field PassThroughOffset

The offset from the beginning of this structure to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct_ex">SCSI_PASS_THROUGH_DIRECT_EX</a> structure that is configured in the same manner as it is for an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct_ex">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request.


### -field Version

Should be zero.


### -field Length

The size of the <b>MPIO_PASS_THROUGH_PATH_DIRECT_EX</b> structure.


### -field Flags



###### 



########## 


### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct_ex">SCSI_PASS_THROUGH_DIRECT_EX</a> structure.


### -field MpioPathId

The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.


## -remarks



<div class="alert"><b>Note</b>  All 32 bit processes running on a 64 bit version of Windows must use the <b>MPIO_PASS_THROUGH_PATH_DIRECT32_EX</b> structure when issuing an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_mpio_pass_through_path_direct_ex">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</a> request.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_mpio_pass_through_path_direct_ex">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct_ex">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through_direct_ex">SCSI_PASS_THROUGH_DIRECT_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

