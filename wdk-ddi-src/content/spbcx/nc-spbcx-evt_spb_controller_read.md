---
UID: NC:spbcx.EVT_SPB_CONTROLLER_READ
title: EVT_SPB_CONTROLLER_READ (spbcx.h)
description: An SPB controller driver's EvtSpbControllerIoRead event callback function reads data from the specified target device into the buffers that are supplied with the read request.
old-location: spb\evtspbcontrollerioread.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["EVT_SPB_CONTROLLER_READ callback function"]
ms.keywords: EVT_SPB_CONTROLLER_READ, EVT_SPB_CONTROLLER_READ callback, EvtSpbControllerIoRead, EvtSpbControllerIoRead callback function [Buses], SPB.evtspbcontrollerioread, spbcx/EvtSpbControllerIoRead
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
 - EVT_SPB_CONTROLLER_READ
 - spbcx/EVT_SPB_CONTROLLER_READ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EVT_SPB_CONTROLLER_READ
---

# EVT_SPB_CONTROLLER_READ callback function

## -description

An SPB controller driver's *EvtSpbControllerIoRead* event callback function reads data from the specified target device into the buffers that are supplied with the read request.

## -parameters

### -param Controller

[in]
A WDFDEVICE handle to the [framework device object](/windows-hardware/drivers/wdf/framework-device-object) that represents the SPB controller.

### -param Target

[in]
An [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the [EvtSpbTargetConnect](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect) callback that opened the connection to the target.

### -param Request

[in]
An [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see [Remarks](#remarks).

### -param Length

[in]
The number of bytes to read from the target device.

## -remarks

SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's *EvtSpbControllerIoRead* callback function when a client (peripheral driver) of the SPB controller sends an [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) request to a target device that is attached to the bus. The *Request* parameter value is a handle that encapsulates this request.

An *EvtSpbControllerIoRead* callback does not return a status value. Instead, the SPB controller driver indicates the status of the read operation in the completion status for the I/O request.

An *EvtSpbControllerIoRead* callback is asynchronous. That is, the callback function should initiate the requested read operation and then return without waiting for the operation to complete. Later, the SPB controller driver completes the read request during an interrupt DPC or a timer DPC.

If the read operation completes in full, the SPB controller driver should set the completion status to STATUS_SUCCESS. If the target device indicates that it can supply some but not all of the data requested, the SPB controller driver should retrieve as much data as is available, specify the number of data bytes retrieved, and set the completion status in the I/O request to STATUS_SUCCESS. Such a partially completed read operation cannot occur on an SPI or I<sup>2</sup>C bus, but might occur on another type of bus.

If the read operation fails due to line noise, a controller hardware error, or a driver error, then the SPB controller driver should set the completion status in the I/O request to an appropriate error code. Not all buses provide a mechanism for a target device to report a transport error or a partially completed transfer, and not all controllers can detect these conditions.

To register an *EvtSpbControllerIoRead* callback function, call the [SpbDeviceInitialize](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize) method.

### Examples

To define an *EvtSpbControllerIoRead* callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *EvtSpbControllerIoRead* callback function that is named `MyEvtSpbControllerIoRead`, use the EVT_SPB_CONTROLLER_READ function type, as shown in this code example:

```cpp
EVT_SPB_CONTROLLER_READ  MyEvtSpbControllerIoRead;
```

Then, implement your callback function as follows:

```cpp
_Use_decl_annotations_
VOID
  MyEvtSpbControllerIoRead(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST Request,
    size_t Length
    )
{ ... }
```

The EVT_SPB_CONTROLLER_READ function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the *Use_decl_annotations* annotation to your function definition. The *Use_decl_annotations* annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_READ function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for KMDF Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers). For more information about *Use_decl_annotations*, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

* [EvtSpbControllerIoSequence](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence)
* [EvtSpbTargetConnect](/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect)
* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read)
* [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SpbDeviceInitialize](/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize)
