---
UID: NC:spbcx.EVT_SPB_TARGET_DISCONNECT
title: EVT_SPB_TARGET_DISCONNECT (spbcx.h)
description: An SPB controller driver's EvtSpbTargetDisconnect event callback function closes a connection to a target device that was previously opened by a call to the driver's EvtSpbTargetConnect event callback function.
old-location: spb\evtspbtargetdisconnect.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["EVT_SPB_TARGET_DISCONNECT callback function"]
ms.keywords: EVT_SPB_TARGET_DISCONNECT, EVT_SPB_TARGET_DISCONNECT callback, EvtSpbTargetDisconnect, EvtSpbTargetDisconnect callback function [Buses], SPB.evtspbtargetdisconnect, spbcx/EvtSpbTargetDisconnect
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
req.irql: Called at PASSIVE_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SPB_TARGET_DISCONNECT
 - spbcx/EVT_SPB_TARGET_DISCONNECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Spbcx.h
api_name:
 - EvtSpbTargetDisconnect
---

# EVT_SPB_TARGET_DISCONNECT callback function


## -description

An SPB controller driver's <i>EvtSpbTargetDisconnect</i> event callback function closes a connection to a target device that was previously opened by a call to the driver's  <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> event callback function.

## -parameters

### -param Controller 

[in]
A WDFDEVICE handle to the <a href="/windows-hardware/drivers/wdf/framework-device-object">framework device object</a> that represents the SPB controller.

### -param Target 

[in]
A <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target to close. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> callback that opened the connection to the target.

## -remarks

Implementation of this function by the SPB controller driver is optional.

SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbTargetDisconnect</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller driver sends an <a href="/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> request to close an SPBTARGET handle. This handle represents a connection to a target device on the bus that the client opened in a previous <a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request. If the <i>EvtSpbTargetDisconnect</i> function returns an error code, SpbCx fails the <b>IRP_MJ_CLOSE</b> request.

The <i>EvtSpbTargetDisconnect</i> function is called synchronously from the context of the client's closing thread after all client-initiated I/O operations have ended and after the client has unlocked the controller (if the client previously locked the controller).

If the SPB controller driver has allocated I/O requests and sent them to the next-lower driver in the I/O-request chain for the target device, the <i>EvtSpbTargetDisconnect</i> function should cancel these requests before it returns.

A client driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchCleanup</a> and <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">CreateProcessNotifyEx</a> callback routines can be called at any time after the <i>EvtSpbTargetDisconnect</i> callback returns. When the client driver's process exits, its <i>CreateProcessNotifyEx</i> routine is called just before the last thread to exit the process is destroyed.

To register an <i>EvtSpbTargetDisconnect</i> callback function, call the <a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method.


#### Examples

To define an <i>EvtSpbTargetDisconnect</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbTargetDisconnect</i> callback function that is named <code>MyEvtSpbTargetDisconnect</code>, use the EVT_SPB_TARGET_DISCONNECT function type, as shown in this code example:


```
EVT_SPB_TARGET_DISCONNECT  MyEvtSpbTargetDisconnect;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
VOID
  MyEvtSpbTargetDisconnect(
    WDFDEVICE Controller,
    SPBTARGET Target
    )
{ ... }
```

The EVT_SPB_TARGET_DISCONNECT function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_TARGET_DISCONNECT function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>
