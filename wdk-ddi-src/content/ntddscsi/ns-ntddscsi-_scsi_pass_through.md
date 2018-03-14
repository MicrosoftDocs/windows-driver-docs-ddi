---
UID: NS:ntddscsi._SCSI_PASS_THROUGH
title: "_SCSI_PASS_THROUGH"
author: windows-driver-content
description: The SCSI_PASS_THROUGH structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through.htm
old-project: storage
ms.assetid: 7470af45-3ebe-44d4-8066-62a69636c20e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_PASS_THROUGH, PSCSI_PASS_THROUGH, PSCSI_PASS_THROUGH structure pointer [Storage Devices], SCSI_PASS_THROUGH, SCSI_PASS_THROUGH structure [Storage Devices], _SCSI_PASS_THROUGH, ntddscsi/PSCSI_PASS_THROUGH, ntddscsi/SCSI_PASS_THROUGH, storage.scsi_pass_through, structs-scsibus_6d017ae1-d61d-49b8-bfaf-b6b15341732b.xml"
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
-	SCSI_PASS_THROUGH
product: Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH, *PSCSI_PASS_THROUGH
---

# _SCSI_PASS_THROUGH structure


## -description


The SCSI_PASS_THROUGH structure is used in conjunction with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a> request to instruct the port driver to send an embedded SCSI command to the target device. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SCSI_PASS_THROUGH {
  USHORT    Length;
  UCHAR     ScsiStatus;
  UCHAR     PathId;
  UCHAR     TargetId;
  UCHAR     Lun;
  UCHAR     CdbLength;
  UCHAR     SenseInfoLength;
  UCHAR     DataIn;
  ULONG     DataTransferLength;
  ULONG     TimeOutValue;
  ULONG_PTR DataBufferOffset;
  ULONG     SenseInfoOffset;
  UCHAR     Cdb[16];
} SCSI_PASS_THROUGH, *PSCSI_PASS_THROUGH;
````


## -struct-fields




### -field Length

Contains the value of <b>sizeof</b>(SCSI_PASS_THROUGH).  


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

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.


### -field DataBufferOffset

Contains an offset from the beginning of this structure to the data buffer. The offset must respect the data alignment requirements of the device.


### -field SenseInfoOffset

Offset from the beginning of this structure to the request-sense buffer. 


### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device. 


## -remarks



The SCSI_PASS_THROUGH structure is used with <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>, which is a buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>. When handling an IOCTL_SCSI_PASS_THROUGH_DIRECT request, the system locks down the buffer in user memory and the device accesses this memory directly. 

The members of SCSI_PASS_THROUGH correspond roughly to the members of a <a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> structure. The values of the <b>DataIn</b> member correspond to the SCSI_IOCTL_DATA_IN, SCSI_IOCTL_DATA_OUT, and SCSI_IOCTL_DATA_UNSPECIFIED flags assigned to <b>SrbFlags</b> member of SCSI_REQUEST_BLOCK. 




## -see-also

<a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_PASS_THROUGH structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

