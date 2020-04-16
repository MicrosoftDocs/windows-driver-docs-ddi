---
UID: NF:wdm.IoBuildDeviceIoControlRequest
title: IoBuildDeviceIoControlRequest function (wdm.h)
description: The IoBuildDeviceIoControlRequest routine allocates and sets up an IRP for a synchronously processed device control request.
old-location: kernel\iobuilddeviceiocontrolrequest.htm
tech.root: kernel
ms.assetid: dde2a45d-9257-4d94-928a-e25f112b2773
ms.date: 04/30/2018
keywords: ["IoBuildDeviceIoControlRequest function"]
ms.keywords: IoBuildDeviceIoControlRequest, IoBuildDeviceIoControlRequest routine [Kernel-Mode Driver Architecture], k104_dca88c92-682a-437e-963b-6fac4e9c39bf.xml, kernel.iobuilddeviceiocontrolrequest, wdm/IoBuildDeviceIoControlRequest
f1_keywords:
 - "wdm/IoBuildDeviceIoControlRequest"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoBuildDeviceControlNoFree, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildDeviceIoControlSetEvent, IrqlIoPassive1, PowerIrpDDis, SignalEventInCompletion, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoBuildDeviceIoControlRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoBuildDeviceIoControlRequest function


## -description


The <b>IoBuildDeviceIoControlRequest</b> routine allocates and sets up an IRP for a synchronously processed device control request.


## -parameters




### -param IoControlCode [in]

Supplies the I/O control code (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">IOCTL</a>) to be used in the request. For information about device type-specific I/O control codes, see device type-specific sections in the Windows Driver Kit (WDK). 


### -param DeviceObject [in]

Supplies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure for the next-lower driver's device object, which represents the target device.


### -param InputBuffer [in, optional]

Supplies a pointer to an input buffer to be passed to the lower driver, or <b>NULL</b> if the request does not pass input data to lower drivers.


### -param InputBufferLength [in]

Supplies the length, in bytes, of the input buffer. If <i>InputBuffer</i> is <b>NULL</b>, <i>InputBufferLength</i> must be zero.


### -param OutputBuffer [out, optional]

Supplies a pointer to an output buffer in which the lower driver is to return data, or <b>NULL</b> if the request does not require lower drivers to return data.


### -param OutputBufferLength [in]

Supplies the length, in bytes, of the output buffer. If <i>OutputBuffer</i> is <b>NULL</b>, <i>OutputBufferLength</i> must be zero.


### -param InternalDeviceIoControl [in]

If <b>TRUE</b>, the routine sets the IRP's major function code to <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>. Otherwise, the routine sets the IRP's major function code to <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>.


### -param Event [in, optional]

Supplies a pointer to a caller-allocated and initialized event object. The I/O manager sets the event to the Signaled state when a lower-level driver completes the requested operation. After calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>, the driver can wait for the event object. The <i>Event</i> parameter is optional and can be set to NULL. However, if <i>Event</i> is NULL, the caller must supply an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine for the IRP to notify the caller when the operation completes.


### -param IoStatusBlock [out]

Specifies an I/O status block to be set when the request is completed by lower drivers.


## -returns



If the operation succeeds, <b>IoBuildDeviceIoControlRequest</b> returns a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>, with the next-lower driver's I/O stack location set up from the supplied parameters. Otherwise, the routine returns <b>NULL</b>.




## -remarks



A driver can call <b>IoBuildDeviceIoControlRequest</b> to set up IRPs for device control requests that it synchronously sends to lower-level drivers.

After calling <b>IoBuildDeviceIoControlRequest</b> to create a request, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a> to send the request to the next-lower driver. If <b>IoCallDriver</b> returns STATUS_PENDING, the driver must wait for the completion of the IRP by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a> on the given <i>Event</i>. Most drivers do not need to set an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine for the IRP.

IRPs that are created by <b>IoBuildDeviceIoControlRequest</b> must be completed by a driver's call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>. A driver that calls <b>IoBuildDeviceIoControlRequest</b> must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/storport-iofreeirp">IoFreeIrp</a>, because the I/O manager frees these synchronous IRPs after <b>IoCompleteRequest</b> has been called.

<b>IoBuildDeviceIoControlRequest</b> queues the IRPs that it creates to an IRP queue that is specific to the current thread. If the thread exits, the I/O manager cancels the IRP.

If the caller supplies an <i>InputBuffer</i> or <i>OutputBuffer</i> parameter, this parameter must point to a buffer that resides in system memory. The caller is responsible for validating any parameter values that it copies into the input buffer from a user-mode buffer. The input buffer might contain parameter values that are interpreted differently depending on whether the originator of the request is a user-mode application or a kernel-mode driver. In the IRP that <b>IoBuildDeviceIoControlRequest</b> returns, the <b>RequestorMode</b> field is always set to <b>KernelMode</b>. This value indicates that the request, and any information contained in the request, is from a trusted, kernel-mode component.

If the caller cannot validate parameter values that it copies from a user-mode buffer to the input buffer, or if these values must not be interpreted as coming from a kernel-mode component, the caller should set the <b>RequestorMode</b> field in the IRP to <b>UserMode</b>. This setting informs the driver that handles the I/O control request that the buffer contains untrusted, user-mode data.

The actual method by which the contents of the <i>InputBuffer</i> and <i>OutputBuffer</i> parameters are stored in the IRP depends on the <i>TransferType</i> value for the IOCTL. For more information about this value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/buffer-descriptions-for-i-o-control-codes">Buffer Descriptions for I/O Control Codes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

