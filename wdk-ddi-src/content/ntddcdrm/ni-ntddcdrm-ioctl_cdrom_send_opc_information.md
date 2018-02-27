---
UID: NI:ntddcdrm.IOCTL_CDROM_SEND_OPC_INFORMATION
title: IOCTL_CDROM_SEND_OPC_INFORMATION
author: windows-driver-content
description: The IOCTL_CDROM_SEND_OPC_INFORMATION control code can be used in file systems and other implementations that want to perform the Optimum Power Calibration (OPC) procedure in advance, so that the first streaming write does not have to wait for the procedure to finish. The optical drive performs the OPC procedure to determine the optimum power of the laser during write. The procedure is necessary to ensure quality, but it wears out the media and should not be performed too often.
old-location: storage\ioctl_cdrom_send_opc_information.htm
old-project: storage
ms.assetid: 77289AB6-7733-4DA1-B4E9-585AA73D137C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_CDROM_SEND_OPC_INFORMATION, IOCTL_CDROM_SEND_OPC_INFORMATION control code [Storage Devices], ntddcdrm/IOCTL_CDROM_SEND_OPC_INFORMATION, storage.ioctl_cdrom_send_opc_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Winioctl.h
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
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_SEND_OPC_INFORMATION
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_SEND_OPC_INFORMATION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_CDROM_SEND_OPC_INFORMATION</b> 
   control code can be used in  file systems and other implementations that want to perform the Optimum Power Calibration (OPC) procedure in advance, so that the first streaming write does not have to wait for the procedure to finish. The optical drive performs the OPC procedure to determine the optimum power of the laser during write. The procedure is necessary to ensure quality, but it wears out the media and should not be performed too often.

To perform this operation, call the 
   <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> 
   function with   <b>IOCTL_CDROM_SEND_OPC_INFORMATION</b> as the <i>dwIoControlCode</i> parameter.


## -ioctlparameters




### -input-buffer


<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a>



### -input-buffer-length

Length of a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a>.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. 

Because of  status code propagation from other APIs, the <b>Status</b> field can be set to (but is not limited to) the following:




#### -STATUS_INFO_LENGTH_MISMATCH

The input buffer length is smaller than required.


#### -STATUS_INVALID_PARAMETER

The request type is not <b>SimpleOpcInfo</b>.


#### -STATUS_SUCCESS

The request completed successfully.


## -remarks



The <b>IOCTL_CDROM_SEND_OPC_INFORMATION</b> IOCTL is a wrapper over the SEND OPC INFORMATION command of the MMC specification. The <b>Exclude0</b> and <b>Exclude1</b> fields directly map to the SEND OPC INFORMATION fields with the same names.

On failures, this IOCTL returns standard errors, such as STATUS_DEVICE_NOT_READY, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR.






## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a>



<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_SEND_OPC_INFORMATION control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

