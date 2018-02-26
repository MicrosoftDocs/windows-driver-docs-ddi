---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_EX
title: "_SCSI_PASS_THROUGH_EX"
author: windows-driver-content
description: The SCSI_PASS_THROUGH_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_ex.htm
old-project: storage
ms.assetid: 3D00B42C-7320-4044-BA7D-71A9BD05B30E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PSCSI_PASS_THROUGH_EX, ,, A, C, E, G, H, I, O, P, PSCSI_PASS_THROUGH_EX, PSCSI_PASS_THROUGH_EX structure pointer [Storage Devices], R, S, SCSI_PASS_THROUGH_EX, SCSI_PASS_THROUGH_EX structure [Storage Devices], T, U, X, _, _SCSI_PASS_THROUGH_EX, ntddscsi/PSCSI_PASS_THROUGH_EX, ntddscsi/SCSI_PASS_THROUGH_EX, storage.scsi_pass_through_ex"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddscsi.h
apiname:
-	SCSI_PASS_THROUGH_EX
product: Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_EX, *PSCSI_PASS_THROUGH_EX
---

# _SCSI_PASS_THROUGH_EX structure


## -description


The <b>SCSI_PASS_THROUGH_EX</b> structure is used in conjunction with an <b>IOCTL_SCSI_PASS_THROUGH_EX</b> request to instruct the port driver to send an embedded SCSI command to the target device. <b>SCSI_PASS_THROUGH_EX</b> can contain a bi-directional data transfers and a variable length command data block.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SCSI_PASS_THROUGH_EX {
  USHORT    Version;
  USHORT    Length;
  ULONG     CdbLength;
  UCHAR     StorAddressLength;
  UCHAR     ScsiStatus;
  UCHAR     SenseInfoLength;
  UCHAR     DataDirection;
  UCHAR     Reserved;
  ULONG     TimeOutValue;
  ULONG     StorAddressOffset;
  ULONG     SenseInfoOffset;
  ULONG     DataOutTransferLength;
  ULONG     DataInTransferLength;
  ULONG_PTR DataOutBufferOffset;
  ULONG_PTR DataInBufferOffset;
  UCHAR     Cdb[ANYSIZE_ARRAY];
} SCSI_PASS_THROUGH_EX, *PSCSI_PASS_THROUGH_EX;
````


## -struct-fields




### -field Version

The version of this structure. Set to 0.


### -field Length

The size of the this structure. Set to <b>sizeof</b>(SCSI_PASS_THROUGH_EX).


### -field CdbLength

Indicates the size in bytes of the SCSI command descriptor block in <b>Cdb</b>.


### -field StorAddressLength

The length of the storage device address structure at the offset of <b>StorAddressOffset</b> after this structure.


### -field ScsiStatus

Reports the SCSI status that was returned by the HBA or the target device.


### -field SenseInfoLength

Indicates the size in bytes of the request-sense buffer. This member is optional and can be set to 0.


### -field DataDirection



#####  This field must have one of these values:



######## 


### -field Reserved

Reserved. Set to 0.


### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.


### -field StorAddressOffset

The location of the target storage device address structure, in bytes, from the beginning of this structure.


### -field SenseInfoOffset

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.


### -field DataOutTransferLength

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataOutTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.


### -field DataInTransferLength

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataInTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.


### -field DataOutBufferOffset

Contains an offset from the beginning of this structure to the output data buffer. The offset must respect the data alignment requirements of the device.


### -field DataInBufferOffset

Contains an offset from the beginning of this structure to the input data buffer. The offset must respect the data alignment requirements of the device.


### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device.


## -remarks



The <b>SCSI_PASS_THROUGH_EX</b> structure is used with the  <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a> control code, which is a buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>. When handling an <b>IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</b> request, the system locks down the buffer in user memory and the device accesses this memory directly. 

<div class="alert"><b>Note</b>  Drivers executing on a 64 bit version of Windows must use the <b>SCSI_PASS_THROUGH32_EX</b> structure as the request data type  when handling an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a> request from a 32 bit process.</div>
<div> </div>



## -see-also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_PASS_THROUGH_EX structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

