---
UID: NC:spbcx.EVT_SPB_CONTROLLER_SEQUENCE
title: EVT_SPB_CONTROLLER_SEQUENCE (spbcx.h)
description: An SPB controller driver's EvtSpbControllerIoSequence event callback function performs a sequence of data transfers between the specified target device and the buffers that are supplied with the sequence request.
old-location: spb\evtspbcontrolleriosequence.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["EVT_SPB_CONTROLLER_SEQUENCE callback function"]
ms.keywords: EVT_SPB_CONTROLLER_SEQUENCE, EVT_SPB_CONTROLLER_SEQUENCE callback, EvtSpbControllerIoSequence, EvtSpbControllerIoSequence callback function [Buses], SPB.evtspbcontrolleriosequence, spbcx/EvtSpbControllerIoSequence
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
 - EVT_SPB_CONTROLLER_SEQUENCE
 - spbcx/EVT_SPB_CONTROLLER_SEQUENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EVT_SPB_CONTROLLER_SEQUENCE
---

# EVT_SPB_CONTROLLER_SEQUENCE callback function

## -description

An SPB controller driver's *EvtSpbControllerIoSequence* event callback function performs a sequence of data transfers between the specified target device and the buffers that are supplied with the sequence request.

## -parameters

### -param Controller [in]


A WDFDEVICE handle to the [framework device object](/windows-hardware/drivers/wdf/framework-device-object) that represents the SPB controller.

### -param Target [in]


An [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the [EvtSpbTargetConnect](./nc-spbcx-evt_spb_target_connect.md) callback that opened the connection to the target.

### -param Request [in]


The [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see [Remarks](#remarks).

### -param TransferCount [in]


The number of individual transfers in this I/O transfer sequence. Each individual transfer is a simple read or write operation.

## -remarks

SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's *EvtSpbControllerIoSequence* callback function when a client (peripheral driver) of the SPB controller sends an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) request to a target device that is attached to the bus. The *Request* parameter value is a handle that encapsulates this request.

An *EvtSpbControllerIoSequence* callback does not return a status value. Instead, the SPB controller driver indicates the status of the sequence operation in the completion status for the I/O request.

An *EvtSpbControllerIoSequence* callback is asynchronous. That is, the callback function should initiate the requested sequence (or the first part of the sequence) operation and then return without waiting for the operation to complete. Later, the SPB controller driver continues processing the request or completes it during interrupt DPCs or timer DPCs.

The SPB controller driver can retrieve the parameter values from the I/O request to determine the maximum length of the transfers within the sequence.  The driver can use this length to allocate DMA resources that it can reuse for each transfer within the sequence.

The SPB controller driver can call the [SpbRequestGetTransferParameters](./nf-spbcx-spbrequestgettransferparameters.md) method to retrieve the control parameters and data buffer for each transfer in the sequence. The buffer is a WDFMEMORY object that, in the current implementation, encapsulates a chained MDL. For more information about chained MDLs, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).

The SPB controller should keep the target device selected for the entire sequence operation. If the target is selected by a device-select line, the line can be asserted continuously from the start of the first transfer in the sequence until the last transfer ends. This line can be asserted as early as the lock operation at the start of the sequence and can remain asserted until the unlock operation at the end of the sequence.

An optional delay can be specified for each transfer in a sequence. The SPB controller driver is responsible for delaying at least that number of microseconds before starting the transfer. If the first transfer in the sequence has an associated delay, the driver should first transmit the address or assert the device-select line of the target device, and then delay for the specified time before starting the data transfer. During this delay, the target should remain selected but the controller should not run the clock on the bus.

If the target device signals a NACK during a transfer in a sequence, the SPB controller stops the sequence. (That is, the controller does not retry the failing transfer and does not try to perform the remaining transfers in the sequence.) If this occurs, the SPB controller driver should set the completion status of the I/O request to STATUS_SUCCESS, set the **Information** field in the I/O status block to the number of bytes actually transferred (not counting the data lost in the transfer that received the NACK), and complete the request.

The SPB controller driver should complete the I/O request with an error status code only if one of the following conditions occurs:

* The SPB controller cannot select the target device (for example, a target device on an I<sup>2</sup>C bus signals a NACK when the controller transmits the address byte).
* The SPB controller driver gets an error status from a call to a WDF or WDM service while processing the sequence operation.

To register an *EvtSpbControllerIoSequence* callback function, call the [SpbDeviceInitialize](./nf-spbcx-spbdeviceinitialize.md) method.

### Examples

To define an *EvtSpbControllerIoSequence* callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *EvtSpbControllerIoSequence* callback function that is named `MyEvtSpbControllerIoSequence`, use the EVT_SPB_CONTROLLER_SEQUENCE function type, as shown in this code example:

```cpp
EVT_SPB_CONTROLLER_SEQUENCE  MyEvtSpbControllerIoSequence;
```

Then, implement your callback function as follows:

```cpp
_Use_decl_annotations_
VOID
  MyEvtSpbControllerIoSequence(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST Request,
    ULONG TransferCount
    )
{ ... }
```

The EVT_SPB_CONTROLLER_SEQUENCE function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the *Use_decl_annotations* annotation to your function definition. The *Use_decl_annotations* annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_SEQUENCE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for KMDF Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers). For more information about *Use_decl_annotations*, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

* [EvtSpbTargetConnect](./nc-spbcx-evt_spb_target_connect.md)
* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read)
* [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write)
* [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SpbDeviceInitialize](./nf-spbcx-spbdeviceinitialize.md)
* [SpbRequestGetTransferParameters](./nf-spbcx-spbrequestgettransferparameters.md)