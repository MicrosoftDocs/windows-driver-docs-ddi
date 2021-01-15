---
UID: NC:spbcx.EVT_SPB_CONTROLLER_OTHER
title: EVT_SPB_CONTROLLER_OTHER (spbcx.h)
description: An SPB controller driver's EvtSpbControllerIoOther event callback function handles device I/O control requests that are not handled by other event callback functions or by the SPB framework extension (SpbCx).
old-location: spb\evtspbcontrollerioother.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["EVT_SPB_CONTROLLER_OTHER callback function"]
ms.keywords: EVT_SPB_CONTROLLER_OTHER, EVT_SPB_CONTROLLER_OTHER callback, EvtSpbControllerIoOther, EvtSpbControllerIoOther callback function [Buses], SPB.evtspbcontrollerioother, spbcx/EvtSpbControllerIoOther
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
 - EVT_SPB_CONTROLLER_OTHER
 - spbcx/EVT_SPB_CONTROLLER_OTHER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EVT_SPB_CONTROLLER_OTHER
---

# EVT_SPB_CONTROLLER_OTHER callback function


## -description

An SPB controller driver's <i>EvtSpbControllerIoOther</i> event callback function handles device I/O control requests that are not handled by other event callback functions or by the SPB framework extension (SpbCx).

## -parameters

### -param Controller 

[in]
A WDFDEVICE handle to the <a href="/windows-hardware/drivers/wdf/framework-device-object">framework device object</a> that represents the SPB controller.

### -param Target 

[in]
An <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> callback that opened the connection to the target.

### -param Request 

[in]
The <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. Your SPB controller driver must complete this request. For more information, see Remarks.

### -param OutputBufferLength 

[in]
The length, in bytes, of the output buffer, if an output buffer is supplied with the request.

### -param InputBufferLength 

[in]
The length, in bytes, of the input buffer, if an input buffer is supplied with the request.

### -param IoControlCode 

[in]
The I/O control code (IOCTL) for the request. This value is an IOCTL that the SPB framework extension (SpbCx) does not recognize.  For more information, see Remarks.

## -remarks

SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbControllerIoOther</i> callback function, SpbCx calls this function when a device I/O control request that SpbCx does not support arrives in the controller's I/O queue. The <i>Request</i> parameter value is a handle that encapsulates this request. The SPB controller driver must complete this request either by performing the requested operation or by returning an error status. If the driver does not support the specified IOCTL, the driver should return the STATUS_NOT_SUPPORTED error status. For a list of IOCTLs that SpbCx supports, see <a href="/previous-versions/hh450915(v=vs.85)">SpbCx I/O Control Codes</a>.

The <i>EvtSpbControllerIoOther</i> callback enables bus-specific or driver-specific commands to be dispatched to the SPB controller driver as IOCTLs. For example, clients (peripheral drivers) might use these IOCTLs to coordinate bus-specific operations, such as full-duplex data exchanges with a target device on an SPI bus. Such IOCTLs are subject to the same flow-control as the IOCTLs that are supported by SpbCx.

The <i>EvtSpbControllerIoOther</i> callback function is similar to the <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a> and processes IOCTLs in a similar way. For general information about how WDF drivers handle I/O requests, see <a href="/windows-hardware/drivers/wdf/framework-request-objects">Framework Request Objects</a>.

An <i>EvtSpbControllerIoOther</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the requested operation in the completion status for the I/O request.

If an I/O request cannot be completed immediately, the callback function should return without waiting for the SPB controller driver to finish processing the request. The SPB controller driver can later complete the request asynchronously.

An <i>EvtSpbControllerIoOther</i> function must validate the parameter values in the I/O control requests that it receives from user-mode clients. For all <i>EvtSpb</i>Xxx callback functions other than <i>EvtSpbControllerIoOther</i>, SpbCx validates the user-mode parameters before it calls the function.

To register an <i>EvtSpbControllerIoOther</i> callback function, call the <a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbcontrollersetioothercallback">SpbControllerSetIoOther</a> method.


#### Examples

To define an <i>EvtSpbControllerIoOther</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbControllerIoOther</i> callback function that is named <code>MyEvtSpbControllerIoOther</code>, use the EVT_SPB_CONTROLLER_OTHER function type, as shown in this code example:


```
EVT_SPB_CONTROLLER_OTHER  MyEvtSpbControllerIoOther;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
VOID
  MyEvtSpbControllerIoOther(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST Request,
    size_t OutputBufferLength,
    size_t InputBufferLength,
    ULONG IoControlCode
    )
{ ... }
```

The EVT_SPB_CONTROLLER_OTHER function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_OTHER function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbcontrollersetioothercallback">SpbControllerSetIoOther</a>

