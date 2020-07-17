---
UID: NI:ntddscsi.IOCTL_SCSI_PASS_THROUGH
title: IOCTL_SCSI_PASS_THROUGH (ntddscsi.h)
description: Allows an application to send almost any SCSI command to a target device, with the following restrictions:Multitarget commands, such as COPY, are not allowed.Bidirectional data transfer operations are not supported.If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit (LU) only if there is no class driver for the type of device that is connected to that LU. The system port driver does not check to determine if a device has been claimed by a class driver before it processes a pass-through request. Therefore, if an application bypasses a class driver that has claimed a device and sends a pass-through request for that device directly to the port driver, a conflict for control of the device can occur between the class driver and the application. If a pass-through request is sent to an adapter device object and if it originates from user mode and targets an LU that is claimed by a class driver, Storport fails the request with STATUS_INVALID_DEVICE_REQUEST. If the request is sent to an LU device object, originates in kernel mode, or targets an unclaimed LU, it is passed to the miniport driver.This request cannot be used if the CDB might require the underlying miniport driver to access memory directly. If the caller's CDB might require direct access to memory, use IOCTL_SCSI_PASS_THROUGH_DIRECT instead. Applications must not attempt to send a pass-through request asynchronously. All pass-through requests must be synchronous. Applications do not require administrative privileges to send a pass-through request to a device, but they must have read/write access to the device. The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. IOCTL_SCSI_PASS_THROUGH is a buffered device control request. To bypass buffering in system memory, callers should use IOCTL_SCSI_PASS_THROUGH_DIRECT. When handling an IOCTL_SCSI_PASS_THROUGH_DIRECT request, the system locks down the buffer in user memory and the device accesses this memory directly. This request is typically used for transferring small amounts of data (<16K).Applications can send this request by means of an IRP_MJ_DEVICE_CONTROL request.Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver.
old-location: storage\ioctl_scsi_pass_through.htm
tech.root: storage
ms.assetid: c7c4a98a-51c3-46c8-856e-053291b412b3
ms.date: 03/29/2018
keywords: ["IOCTL_SCSI_PASS_THROUGH IOCTL"]
ms.keywords: IOCTL_SCSI_PASS_THROUGH, IOCTL_SCSI_PASS_THROUGH control, IOCTL_SCSI_PASS_THROUGH control code [Storage Devices], k307_3ce0bb34-5f8d-40f8-ae98-24f597656ad0.xml, ntddscsi/IOCTL_SCSI_PASS_THROUGH, storage.ioctl_scsi_pass_through
f1_keywords:
 - "ntddscsi/IOCTL_SCSI_PASS_THROUGH"
 - "IOCTL_SCSI_PASS_THROUGH"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddscsi.h
api_name:
- IOCTL_SCSI_PASS_THROUGH
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_PASS_THROUGH IOCTL


## -description



Allows an application to send almost any SCSI command to a target device, with the following restrictions:

<ul>
<li>
Multitarget commands, such as COPY, are not allowed.

</li>
<li>
Bidirectional data transfer operations are not supported.

</li>
<li>
If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit (LU) only if there is no class driver for the type of device that is connected to that LU. The system port driver does not check to determine if a device has been claimed by a class driver before it processes a pass-through request. Therefore, if an application bypasses a class driver that has claimed a device and sends a pass-through request for that device directly to the port driver, a conflict for control of the device can occur between the class driver and the application. If a pass-through request is sent to an adapter device object and if it originates from user mode and targets an LU that is claimed by a class driver, Storport fails the request with STATUS_INVALID_DEVICE_REQUEST. If the request is sent to an LU device object, originates in kernel mode, or targets an unclaimed LU, it is passed to the miniport driver.

</li>
<li>
This request cannot be used if the CDB might require the underlying miniport driver to access memory directly. If the caller's CDB might require direct access to memory, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> instead. 

</li>
<li>
Applications must not attempt to send a pass-through request asynchronously. All pass-through requests must be synchronous. 

</li>
<li>
Applications do not require administrative privileges to send a pass-through request to a device, but they must have read/write access to the device. 

</li>
</ul>
The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. 

<b>IOCTL_SCSI_PASS_THROUGH</b> is a buffered device control request. To bypass buffering in system memory, callers should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>. When handling an <b>IOCTL_SCSI_PASS_THROUGH_DIRECT</b> request, the system locks down the buffer in user memory and the device accesses this memory directly. 

This request is typically used for transferring small amounts of data (<16K).

Applications can send this request by means of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a> request.

Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver. 


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver-overview">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

This structure includes a SCSI CDB, which must be initialized by the caller except for the path, target ID, and logical unit number (LUN), which are filled in by the port driver. For a data-out command, the data to be transferred is included in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> at <b>DataBufferOffset</b> in the <b>SCSI_PASS_THROUGH</b> structure. However, the caller must allocate additional storage, immediately following <b>SCSI_PASS_THROUGH</b>, if the caller asks for request-sense data.


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>, which must be at least (<i>sense data size</i> + <b>sizeof</b>(SCSI_PASS_THROUGH)). The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through">SCSI_PASS_THROUGH</a> structure varies, depending on its <b>DataTransferLength</b> specification.


### -output-buffer

The port driver returns any request-sense data and any data transferred from the device to the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

The <b>SenseInfoLength</b> and <b>DataTransferLength</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through">SCSI_PASS_THROUGH</a> structure are updated to indicate the amount of data transferred.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned in the output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input <b>Length</b> value in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through">SCSI_PASS_THROUGH</a> is improperly set. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_pass_through">SCSI_PASS_THROUGH</a>
 

 

