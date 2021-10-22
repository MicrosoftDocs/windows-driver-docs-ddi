---
UID: NC:spbcx.EVT_SPB_CONTROLLER_LOCK
title: EVT_SPB_CONTROLLER_LOCK (spbcx.h)
description: An SPB controller driver's EvtSpbControllerLock event callback function locks the SPB controller for accesses of a single target device on the bus.
old-location: spb\evtspbcontrollerlock.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["EVT_SPB_CONTROLLER_LOCK callback function"]
ms.keywords: EVT_SPB_CONTROLLER_LOCK, EVT_SPB_CONTROLLER_LOCK callback, EvtSpbControllerLock, EvtSpbControllerLock callback function [Buses], SPB.evtspbcontrollerlock, spbcx/EvtSpbControllerLock
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
 - EVT_SPB_CONTROLLER_LOCK
 - spbcx/EVT_SPB_CONTROLLER_LOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EVT_SPB_CONTROLLER_LOCK
---

# EVT_SPB_CONTROLLER_LOCK callback function

## -description

An SPB controller driver's *EvtSpbControllerLock* event callback function locks the SPB controller for accesses of a single target device on the bus.

## -parameters

### -param Controller [in]


A WDFDEVICE handle to the [framework device object](/windows-hardware/drivers/wdf/framework-device-object) that represents the SPB controller.

### -param Target [in]


An [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the [EvtSpbTargetConnect](./nc-spbcx-evt_spb_target_connect.md) callback that opened the connection to the target.

### -param LockRequest [in]


An [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles) handle to an I/O control request to lock the controller. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see [Remarks](#remarks).

## -remarks

SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an *EvtSpbControllerLock* callback function, SpbCx calls this function when a client (peripheral driver) of the controller sends an [IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code) request to a target on the bus. The *LockRequest* parameter value is a handle that encapsulates this request.

The *EvtSpbControllerLock* and [EvtSpbControllerUnlock](./nc-spbcx-evt_spb_controller_unlock.md) functions perform complementary operations. Both functions are optional. If your SPB controller driver implements an *EvtSpbControllerUnlock* function, the driver is not required to implement an *EvtSpbControllerLock* function, but might do so. However, if your SPB controller driver implements an *EvtSpbControllerLock* function, it must also implement an *EvtSpbControllerUnlock* function. For more information, see Remarks in [SPB_CONTROLLER_CONFIG](./ns-spbcx-_spb_controller_config.md).

While the lock is in effect, the controller must not allow accesses to targets on the bus other than the target designated by the *LockRequest* parameter.

If the SPB controller driver needs to change the mode of its controller to temporarily override the normal target selection mechanism, it can do so during the *EvtSpbControllerLock* callback. If this mode change involves a long delay or requires the driver to wait for a device interrupt, the driver should initiate the mode change and then return from the callback without delay. Later, the driver can complete the lock operation in a timer DPC or an interrupt DPC.

If the lock operation completes in a DPC, the SPB controller driver should previously have allocated all the resources that it needs for the lock operation.

An *EvtSpbControllerLock* callback must avoid failing a lock request. If [Driver Verifier](/windows-hardware/drivers/what-s-new-in-driver-development) is enabled, such a failure will trigger a verifier trap, which will report to the Plug and Play manager that the controller has failed. SpbCx ignores the failure of an lock request and does not try to handle or mitigate the failure.

The *EvtSpbControllerLock* function does not return a value. Instead, the SPB controller driver indicates the status of the lock operation in the completion status of the I/O request that is identified by the *LockRequest* parameter. Set the completion status to STATUS_SUCCESS.

SpbCx calls the [EvtSpbControllerUnlock](./nc-spbcx-evt_spb_controller_unlock.md) event callback function to unlock a controller that was previously locked by an *EvtSpbControllerLock* callback.

To register an *EvtSpbControllerLock* callback function, call the [SpbDeviceInitialize](./nf-spbcx-spbdeviceinitialize.md) method.

For more information about the *EvtSpbControllerLock* function, see [Handling Client-Implemented Sequences](/windows-hardware/drivers/spb/handling-client-implemented-sequences).

### Examples

To define an *EvtSpbControllerLock* callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *EvtSpbControllerLock* callback function that is named `MyEvtSpbControllerLock`, use the EVT_SPB_CONTROLLER_LOCK function type, as shown in this code example:

```cpp
EVT_SPB_CONTROLLER_LOCK  MyEvtSpbControllerLock;
```

Then, implement your callback function as follows:

```cpp
_Use_decl_annotations_
VOID
  MyEvtSpbControllerLock(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST LockRequest
    )
{ ... }
```

The EVT_SPB_CONTROLLER_LOCK function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the *Use_decl_annotations* annotation to your function definition. The *Use_decl_annotations* annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_LOCK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for KMDF Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers). For more information about *Use_decl_annotations*, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

* [EvtSpbControllerUnlock](./nc-spbcx-evt_spb_controller_unlock.md)
* [EvtSpbTargetConnect](./nc-spbcx-evt_spb_target_connect.md)
* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code)
* [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SPBTARGET](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SPB_CONTROLLER_CONFIG](./ns-spbcx-_spb_controller_config.md)
* [SpbDeviceInitialize](./nf-spbcx-spbdeviceinitialize.md)