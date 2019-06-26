---
UID: NC:spbcx.EVT_SPB_TARGET_CONNECT
title: EVT_SPB_TARGET_CONNECT (spbcx.h)
description: An SPB controller driver's EvtSpbTargetConnect event callback function opens a connection to a target device on the bus.
old-location: spb\evtspbtargetconnect.htm
tech.root: SPB
ms.assetid: D90DD169-A989-4D08-B1B8-BDE7EC9B7A82
ms.date: 04/30/2018
ms.keywords: EVT_SPB_TARGET_CONNECT, EVT_SPB_TARGET_CONNECT callback, EvtSpbTargetConnect, EvtSpbTargetConnect callback function [Buses], SPB.evtspbtargetconnect, spbcx/EvtSpbTargetConnect
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Spbcx.h
api_name:
- EvtSpbTargetConnect
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SPB_TARGET_CONNECT callback function


## -description


An SPB controller driver's <i>EvtSpbTargetConnect</i> event callback function opens a connection to a target device on the bus.


## -parameters




### -param Controller [in]

A WDFDEVICE handle to the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-device-object">framework device object</a> that represents the SPB controller.


### -param Target [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target to open.  The target is a peripheral device or port that is attached to the bus.


## -returns



<i>EvtSpbTargetConnect</i> returns STATUS_SUCCESS if the driver successfully opens the connection to the target.  Otherwise, the function returns an appropriate NTSTATUS error code.




## -remarks



Implementation of this function by the SPB controller driver is optional.

The SPB framework extension (SpbCx) manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbTargetConnect</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller sends an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request to open a connection to a target device on the bus. If the <i>EvtSpbTargetConnect</i> function returns an error code, SpbCx fails the <b>IRP_MJ_CREATE</b> request. A client that successfully opens a connection to a target has exclusive access to the target until the connection is closed.

Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbtargetgetconnectionparameters">SpbTargetGetConnectionParameters</a> method to get the connection parameters for the target device. An SPB controller driver typically calls this method from the driver's <i>EvtSpbTargetConnect</i> function. <b>SpbTargetGetConnectionParameters</b> writes the connection parameters to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/ns-spbcx-_spb_connection_parameters">SPB_CONNECTION_PARAMETERS</a> structure. The <b>ConnectionParameters</b> member of this structure is a pointer to a buffer that contains the connection settings for the target device. The driver uses these settings to configure the SPB controller to communicate with the device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/how-to-get-the-connection-settings-for-a-device">How to Get the Connection Settings for a Device</a>.

The <i>EvtSpbTargetConnect</i> callback function is called synchronously from the context of the client thread that requests the connection to the target.

SpbCx calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a> callback function to close a target connection that was previously opened by an <i>EvtSpbTargetConnect</i> callback.

To register an <i>EvtSpbTargetConnect</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method.


#### Examples

To define an <i>EvtSpbTargetConnect</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbTargetConnect</i> callback function that is named <code>MyEvtSpbTargetConnect</code>, use the EVT_SPB_TARGET_CONNECT function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SPB_TARGET_CONNECT  MyEvtSpbTargetConnect;</pre>
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
NTSTATUS
  MyEvtSpbTargetConnect(
    WDFDEVICE Controller,
    SPBTARGET Target
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The EVT_SPB_TARGET_CONNECT function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_TARGET_CONNECT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/ns-spbcx-_spb_connection_parameters">SPB_CONNECTION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>
 

 

