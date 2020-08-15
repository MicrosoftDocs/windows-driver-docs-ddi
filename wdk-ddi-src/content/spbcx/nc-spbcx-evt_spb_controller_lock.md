---
UID: NC:spbcx.EVT_SPB_CONTROLLER_LOCK
title: EVT_SPB_CONTROLLER_LOCK (spbcx.h)
description: An SPB controller driver's EvtSpbControllerLock event callback function locks the SPB controller for accesses of a single target device on the bus.
old-location: spb\evtspbcontrollerlock.htm
tech.root: SPB
ms.assetid: E08674F1-CE63-464B-9C70-96F93C574753
ms.date: 04/30/2018
keywords: ["EVT_SPB_CONTROLLER_LOCK callback function"]
ms.keywords: EVT_SPB_CONTROLLER_LOCK, EVT_SPB_CONTROLLER_LOCK callback, EvtSpbControllerLock, EvtSpbControllerLock callback function [Buses], SPB.evtspbcontrollerlock, spbcx/EvtSpbControllerLock
f1_keywords:
 - "spbcx/EvtSpbControllerLock"
 - "EvtSpbControllerLock"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Spbcx.h
api_name:
- EvtSpbControllerLock
targetos: Windows
req.typenames: 
---

# EVT_SPB_CONTROLLER_LOCK callback function


## -description


An SPB controller driver's <i>EvtSpbControllerLock</i> event callback function locks the SPB controller for accesses of a single target device on the bus.


## -parameters




### -param Controller 
[in]
A WDFDEVICE handle to the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-device-object">framework device object</a> that represents the SPB controller.


### -param Target 
[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> callback that opened the connection to the target.


### -param LockRequest 
[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to an I/O control request to lock the controller.  Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.


## -remarks



SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbControllerLock</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a> request to a target on the bus. The <i>LockRequest</i> parameter value is a handle that encapsulates this request.

The <i>EvtSpbControllerLock</i> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a> functions perform complementary operations. Both functions are optional. If your SPB controller driver implements an <i>EvtSpbControllerUnlock</i> function, the driver is not required to implement an <i>EvtSpbControllerLock</i> function, but might do so. However, if your SPB controller driver implements an <i>EvtSpbControllerLock</i> function, it must also implement an <i>EvtSpbControllerUnlock</i> function. For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a>.

While the lock is in effect, the controller must not allow accesses to targets on the bus other than the target designated by the <i>LockRequest</i> parameter.

If the SPB controller driver needs to change the mode of its controller to temporarily override the normal target selection mechanism, it can do so during the <i>EvtSpbControllerLock</i> callback.  If this mode change involves a long delay or requires the driver to wait for a device interrupt, the driver should initiate the mode change and then return from the callback without delay. Later, the driver can complete the lock operation in a timer DPC or an interrupt DPC.

If the lock operation completes in a DPC, the SPB controller driver should previously have allocated all the resources that it needs for the lock operation.

An <i>EvtSpbControllerLock</i> callback must avoid failing a lock request.  If <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> is enabled, such a failure  will trigger a verifier trap, which will report to the Plug and Play manager that the controller has failed.  SpbCx ignores the failure of an lock request and does not try to handle or mitigate the failure.

The <i>EvtSpbControllerLock</i> function does not return a value.  Instead, the SPB controller driver indicates the status of the lock operation in the completion status of the I/O request that is identified by the <i>LockRequest</i> parameter. Set the completion status to STATUS_SUCCESS.

SpbCx calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a> event callback function to unlock a controller that was previously locked by an <i>EvtSpbControllerLock</i> callback.

To register an <i>EvtSpbControllerLock</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method.

For more information about the <i>EvtSpbControllerLock</i> function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/handling-client-implemented-sequences">Handling Client-Implemented Sequences</a>.


#### Examples

To define an <i>EvtSpbControllerLock</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbControllerLock</i> callback function that is named <code>MyEvtSpbControllerLock</code>, use the EVT_SPB_CONTROLLER_LOCK function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SPB_CONTROLLER_LOCK  MyEvtSpbControllerLock;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyEvtSpbControllerLock(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST LockRequest
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The EVT_SPB_CONTROLLER_LOCK function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_LOCK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_unlock">EvtSpbControllerUnlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>
 

 

