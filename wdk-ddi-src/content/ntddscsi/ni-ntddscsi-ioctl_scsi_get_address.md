---
UID: NI:ntddscsi.IOCTL_SCSI_GET_ADDRESS
title: IOCTL_SCSI_GET_ADDRESS
author: windows-driver-content
description: Returns the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target.
old-location: storage\ioctl_scsi_get_address.htm
old-project: storage
ms.assetid: 56e2a62c-ecf1-45c8-ba65-fb53b1897ddb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_SCSI_GET_ADDRESS, IOCTL_SCSI_GET_ADDRESS control code [Storage Devices], k307_0d205fdd-0951-42ef-bd5c-09727bee65f4.xml, ntddscsi/IOCTL_SCSI_GET_ADDRESS, storage.ioctl_scsi_get_address
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	Ntddscsi.h
apiname:
-	IOCTL_SCSI_GET_ADDRESS
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_GET_ADDRESS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target. A legacy class driver can issue this request to the port driver to obtain the address of its device. This request is not relevant to storage class drivers that support Plug and Play because the port driver supplies the address information on behalf of the class driver.

This request must be directed to a class driver or to a PDO created by the port driver.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

Updated <a href="..\ntddscsi\ns-ntddscsi-_scsi_address.md">SCSI_ADDRESS</a> information is returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(<a href="..\ntddscsi\ns-ntddscsi-_scsi_address.md">SCSI_ADDRESS</a>).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -see-also

<a href="..\ntddscsi\ns-ntddscsi-_scsi_address.md">SCSI_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_GET_ADDRESS control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

