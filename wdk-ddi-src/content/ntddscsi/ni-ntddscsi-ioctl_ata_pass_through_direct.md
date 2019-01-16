---
UID: NI:ntddscsi.IOCTL_ATA_PASS_THROUGH_DIRECT
title: IOCTL_ATA_PASS_THROUGH_DIRECT
description: Allows an application to send almost any ATA command to a target device, with the following restrictions:\_If a class driver for the target type of device exists, the application must send the request to the class driver.
old-location: storage\ioctl_ata_pass_through_direct.htm
tech.root: storage
ms.assetid: 705918c7-c4ea-4495-b87f-2904f7d45ac0
ms.date: 03/29/2018
ms.keywords: IOCTL_ATA_PASS_THROUGH_DIRECT, IOCTL_ATA_PASS_THROUGH_DIRECT control, IOCTL_ATA_PASS_THROUGH_DIRECT control code [Storage Devices], k307_8f1da276-e1bf-405e-8e01-a633b8671d5f.xml, ntddscsi/IOCTL_ATA_PASS_THROUGH_DIRECT, storage.ioctl_ata_pass_through_direct
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
-	Ntddscsi.h
api_name:
-	IOCTL_ATA_PASS_THROUGH_DIRECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_ATA_PASS_THROUGH_DIRECT IOCTL


## -description



Allows an application to send almost any ATA command to a target device, with the following restrictions: 

<ul>
<li>
If a class driver for the target type of device exists, the application must send the request to the class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the device. 

</li>
<li>
The application <i>must</i> use this request rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff559309">IOCTL_ATA_PASS_THROUGH</a> if the embedded ATA command might require the underlying miniport driver to access memory directly. 

</li>
</ul>
If the ATA command requests a data transfer operation, the caller must set up a cache-aligned buffer from which, or into which, the driver can transfer data directly. The IOCTL_ATA_PASS_THROUGH_DIRECT request is typically used for transferring large amounts of data (more than 16 KB).




## -ioctlparameters




### -input-buffer

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size in bytes of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The value of <b>InputBufferLength</b> is fixed and does not depend on the amount of data transferred. It is equal to <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT). If the size of the buffer is less than <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT), the port driver fails the I/O request and returns an error. 

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a> structure that includes a set of task file input registers that indicate the sort of command to be performed. The caller must initialize all the members of this structure except for <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>, which the port driver fills in. For a data-out command, the <b>DataBuffer</b> member of <b>ATA_PASS_THROUGH_DIRECT</b> must point to a cache-aligned buffer containing the data to be written. 


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size in bytes of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The value of <b>InputBufferLength</b> is fixed and does not depend on the amount of data transferred. It is equal to <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT). If the size of the buffer is less than <b>sizeof</b>(ATA_PASS_THROUGH_DIRECT), the port driver fails the I/O request and returns an error. 


### -output-buffer

The port driver formats the return data using an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a> structure that it stores in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 

The port driver stores the transferred data in the cache-aligned buffer pointed to by the <b>DataBuffer</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a>.

The port driver fills the <b>CurrentTaskFile</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a> with the values present in the device's output registers at the completion of the ATA command. The application is responsible for interpreting the contents of the output registers to determine what errors, if any, were returned by the device. 


### -output-buffer-length

The port driver updates the <b>DataTransferLength</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a> structure to indicate the amount of data that was transferred from the device.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the number of bytes returned in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The <b>Status</b> member is set to STATUS_SUCCESS or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in <a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a> is improperly set. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551322">ATA_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559309">IOCTL_ATA_PASS_THROUGH</a>
 

 

