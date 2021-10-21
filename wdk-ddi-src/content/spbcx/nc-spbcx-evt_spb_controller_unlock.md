---
UID: NC:spbcx.EVT_SPB_CONTROLLER_UNLOCK
title: EVT_SPB_CONTROLLER_UNLOCK (spbcx.h)
description: An SPB controller driver's EvtSpbControllerUnlock event callback function unlocks the SPB controller, which was locked by a previous call to the EvtSpbControllerLock event callback function.
old-location: spb\evtspbcontrollerunlock.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["EVT_SPB_CONTROLLER_UNLOCK callback function"]
ms.keywords: EVT_SPB_CONTROLLER_UNLOCK, EVT_SPB_CONTROLLER_UNLOCK callback, EvtSpbControllerUnlock, EvtSpbControllerUnlock callback function [Buses], SPB.evtspbcontrollerunlock, spbcx/EvtSpbControllerUnlock
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
 - EVT_SPB_CONTROLLER_UNLOCK
 - spbcx/EVT_SPB_CONTROLLER_UNLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EVT_SPB_CONTROLLER_UNLOCK
---

# EVT_SPB_CONTROLLER_UNLOCK callback function

## -description

An SPB controller driver's *EvtSpbControllerUnlock* event callback function unlocks the SPB controller, which was locked by a previous call to the [EvtSpbControllerLock](./nc-spbcx-evt_spb_controller_lock.md) event callback function.

## -parameters

### -param Controller

[in]
A WDFDEVICE handle to the [framework device object](/windows-hardware/drivers/wdf/framework-device-object) that represents the SPB controller.

### -param Target

[in]
An [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the [EvtSpbTargetConnect](./nc-spbcx-evt_spb_target_connect.md) callback that opened the connection to the target.

### -param UnlockRequest

[in]
An [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles) handle to an I/O control request to unlock the controller. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see [Remarks](#remarks).

## -remarks

SpbCx manages the I/O queue for the SPB controller. SpbCx calls this function when a client (peripheral driver) of the controller sends an [IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code) request to a target on the bus. The *UnlockRequest* parameter value is a handle that encapsulates this request.

The [EvtSpbControllerLock](./nc-spbcx-evt_spb_controller_lock.md) and *EvtSpbControllerUnlock* functions perform complementary operations. Both functions are optional. If your SPB controller driver implements an *EvtSpbControllerUnlock* function, the driver is not required to implement an *EvtSpbControllerLock* function, but might do so. However, if your SPB controller driver implements an *EvtSpbControllerLock* function, it must also implement an *EvtSpbControllerUnlock* function. For more information, see Remarks in [SPB_CONTROLLER_CONFIG](./ns-spbcx-_spb_controller_config.md).

If the SPB controller driver needs to change the mode of its controller to restore normal target selection, it can do so during the *EvtSpbControllerUnlock* callback. If this change of mode involves a long delay or requires the driver to wait for a device interrupt, the driver should initiate the mode change and then return from the callback without delay. Later, the driver can complete the unlock request in an interrupt DPC or a timer DPC.

An *EvtSpbControllerUnlock* callback must avoid failing an unlock request. If [Driver Verifier](/windows-hardware/drivers/what-s-new-in-driver-development) is enabled, such a failure will trigger a verifier trap, which will report to the Plug and Play manager that the controller has failed. SpbCx ignores the failure of an unlock request and does not try to handle or mitigate the failure.

The *EvtSpbControllerUnlock* function does not return a value. Instead, the SPB controller driver indicates the status of the unlock operation in the completion status of the I/O request that is identified by the *UnlockRequest* parameter. Set the completion status to STATUS_SUCCESS.

To register an *EvtSpbControllerUnlock* callback function, call the [SpbDeviceInitialize](./nf-spbcx-spbdeviceinitialize.md) method.

For more information about the *EvtSpbControllerUnlock* function, see [Handling Client-Implemented Sequences](/windows-hardware/drivers/spb/handling-client-implemented-sequences).

### Examples

To define an *EvtSpbControllerUnlock* callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *EvtSpbControllerUnlock* callback function that is named `MyEvtSpbControllerUnlock`, use the EVT_SPB_CONTROLLER_UNLOCK function type, as shown in this code example:

```cpp
EVT_SPB_CONTROLLER_UNLOCK  MyEvtSpbControllerUnlock;
```

Then, implement your callback function as follows:

```cpp
_Use_decl_annotations_
VOID
  MyEvtSpbControllerUnlock(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST UnlockRequest
    )
{ ... }
```

The EVT_SPB_CONTROLLER_UNLOCK function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the *Use_decl_annotations* annotation to your function definition. The *Use_decl_annotations* annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_UNLOCK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for KMDF Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers). For more information about *Use_decl_annotations*, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

* [EvtSpbControllerLock](./nc-spbcx-evt_spb_controller_lock.md)
* [EvtSpbTargetConnect](./nc-spbcx-evt_spb_target_connect.md)
* [IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code)
* [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SPB_CONTROLLER_CONFIG](./ns-spbcx-_spb_controller_config.md)
* [SpbDeviceInitialize](./nf-spbcx-spbdeviceinitialize.md)