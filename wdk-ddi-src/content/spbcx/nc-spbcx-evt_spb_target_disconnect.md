---
UID: NC:spbcx.EVT_SPB_TARGET_DISCONNECT
title: EVT_SPB_TARGET_DISCONNECT
author: windows-driver-content
description: An SPB controller driver's EvtSpbTargetDisconnect event callback function closes a connection to a target device that was previously opened by a call to the driver's EvtSpbTargetConnect event callback function.
old-location: spb\evtspbtargetdisconnect.htm
tech.root: SPB
ms.assetid: 02756C35-E76C-42C0-80FA-359CADE224A1
ms.date: 04/30/2018
ms.keywords: EVT_SPB_TARGET_DISCONNECT, EVT_SPB_TARGET_DISCONNECT callback, EvtSpbTargetDisconnect, EvtSpbTargetDisconnect callback function [Buses], SPB.evtspbtargetdisconnect, spbcx/EvtSpbTargetDisconnect
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Spbcx.h
api_name:
-	EvtSpbTargetDisconnect
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SPB_TARGET_DISCONNECT callback function


## -description


An SPB controller driver's <i>EvtSpbTargetDisconnect</i> event callback function closes a connection to a target device that was previously opened by a call to the driver's  <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> event callback function.


## -parameters




### -param Controller [in]

A WDFDEVICE handle to the <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> that represents the SPB controller.


### -param Target [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target to close. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback that opened the connection to the target.


## -returns



None.




## -remarks



Implementation of this function by the SPB controller driver is optional.

SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbTargetDisconnect</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller driver sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request to close an SPBTARGET handle. This handle represents a connection to a target device on the bus that the client opened in a previous <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request. If the <i>EvtSpbTargetDisconnect</i> function returns an error code, SpbCx fails the <b>IRP_MJ_CLOSE</b> request.

The <i>EvtSpbTargetDisconnect</i> function is called synchronously from the context of the client's closing thread after all client-initiated I/O operations have ended and after the client has unlocked the controller (if the client previously locked the controller).

If the SPB controller driver has allocated I/O requests and sent them to the next-lower driver in the I/O-request chain for the target device, the <i>EvtSpbTargetDisconnect</i> function should cancel these requests before it returns.

A client driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_dispatch">DispatchCleanup</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559951">CreateProcessNotifyEx</a> callback routines can be called at any time after the <i>EvtSpbTargetDisconnect</i> callback returns. When the client driver's process exits, its <i>CreateProcessNotifyEx</i> routine is called just before the last thread to exit the process is destroyed.

To register an <i>EvtSpbTargetDisconnect</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.


#### Examples

To define an <i>EvtSpbTargetDisconnect</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbTargetDisconnect</i> callback function that is named <code>MyEvtSpbTargetDisconnect</code>, use the EVT_SPB_TARGET_DISCONNECT function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SPB_TARGET_DISCONNECT  MyEvtSpbTargetDisconnect;</pre>
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
  MyEvtSpbTargetDisconnect(
    WDFDEVICE Controller,
    SPBTARGET Target
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The EVT_SPB_TARGET_DISCONNECT function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_TARGET_DISCONNECT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>
 

 

