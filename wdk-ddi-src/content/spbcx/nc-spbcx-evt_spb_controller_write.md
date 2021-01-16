---
UID: NC:spbcx.EVT_SPB_CONTROLLER_WRITE
title: EVT_SPB_CONTROLLER_WRITE (spbcx.h)
description: An SPB controller driver's EvtSpbControllerIoWrite event callback function writes data to the specified target device from the buffers that are supplied with the write request.
old-location: spb\evtspbcontrolleriowrite.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["EVT_SPB_CONTROLLER_WRITE callback function"]
ms.keywords: EVT_SPB_CONTROLLER_WRITE, EVT_SPB_CONTROLLER_WRITE callback, EvtSpbControllerIoWrite, EvtSpbControllerIoWrite callback function [Buses], SPB.evtspbcontrolleriowrite, spbcx/EvtSpbControllerIoWrite
req.header: spbcx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SPB_CONTROLLER_WRITE
 - spbcx/EVT_SPB_CONTROLLER_WRITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EVT_SPB_CONTROLLER_WRITE
---

# EVT_SPB_CONTROLLER_WRITE callback function


## -description

An SPB controller driver's <i>EvtSpbControllerIoWrite</i> event callback function writes data to the specified target device from the buffers that are supplied with the write request.

## -parameters

### -param Controller 

[in]
A WDFDEVICE handle to the <a href="/windows-hardware/drivers/wdf/framework-device-object">framework device object</a> that represents the SPB controller.

### -param Target 

[in]
An <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> callback that opened the connection to the target.

### -param Request 

[in]
An <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.

### -param Length 

[in]
The number of bytes to write to the target device.

## -remarks

SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's <i>EvtSpbControllerIoWrite</i> callback function when a client (peripheral driver) of the SPB controller sends an <a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a> request to a target device that is attached to the bus. The <i>Request</i> parameter value is a handle that encapsulates this request.

An <i>EvtSpbControllerIoWrite</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the write operation in the completion status for the I/O request.

An <i>EvtSpbControllerIoWrite</i> callback is asynchronous.  That is, the callback function should initiate the requested write operation and then return without waiting for the operation to complete. Later, the SPB controller driver completes the write request during an interrupt DPC or a timer DPC.

An <i>EvtSpbControllerIoWrite</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the write operation in the completion status for the I/O request.

If the write operation completes in full, the callback function should set the completion status to STATUS_SUCCESS. If the target device indicates that it cannot accept any more data before a transmission completes, the driver should set the completion status to STATUS_SUCCESS and specify the number of bytes transmitted.

If a transmission error occurs during the write operation, the driver should set the completion status in the I/O request to an appropriate error code. Not all buses provide a mechanism for a target device to report a transport error or a partially completed transfer, and not all controllers can detect these conditions.

To register an <i>EvtSpbControllerIoWrite</i> callback function, call the <a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method.


#### Examples

To define an <i>EvtSpbControllerIoWrite</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbControllerIoWrite</i> callback function that is named <code>MyEvtSpbControllerIoWrite</code>, use the EVT_SPB_CONTROLLER_WRITE function type, as shown in this code example:


```
EVT_SPB_CONTROLLER_WRITE  MyEvtSpbControllerIoWrite;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
VOID
  MyEvtSpbControllerIoWrite(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST Request,
    size_t Length
    )
{ ... }
```

The EVT_SPB_CONTROLLER_WRITE function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_WRITE function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_read">EvtSpbControllerIoRead</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>

