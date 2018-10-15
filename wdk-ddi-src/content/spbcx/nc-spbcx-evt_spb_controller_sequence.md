---
UID: NC:spbcx.EVT_SPB_CONTROLLER_SEQUENCE
title: EVT_SPB_CONTROLLER_SEQUENCE
author: windows-driver-content
description: An SPB controller driver's EvtSpbControllerIoSequence event callback function performs a sequence of data transfers between the specified target device and the buffers that are supplied with the sequence request.
old-location: spb\evtspbcontrolleriosequence.htm
tech.root: SPB
ms.assetid: C56F1528-5FDA-4BC9-AB32-7882FB0F7713
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: EVT_SPB_CONTROLLER_SEQUENCE, EVT_SPB_CONTROLLER_SEQUENCE callback, EvtSpbControllerIoSequence, EvtSpbControllerIoSequence callback function [Buses], SPB.evtspbcontrolleriosequence, spbcx/EvtSpbControllerIoSequence
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Spbcx.h
api_name:
-	EvtSpbControllerIoSequence
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SPB_CONTROLLER_SEQUENCE callback function


## -description


An SPB controller driver's <i>EvtSpbControllerIoSequence</i> event callback function performs a sequence of data transfers between the specified target device and the buffers that are supplied with the sequence request.


## -parameters




### -param Controller [in]

A WDFDEVICE handle to the <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> that represents the SPB controller.


### -param Target [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback that opened the connection to the target.


### -param Request [in]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.


### -param TransferCount [in]

The number of individual transfers in this I/O transfer sequence. Each individual transfer is a simple read or write operation.


## -returns



None.




## -remarks



SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's <i>EvtSpbControllerIoSequence</i> callback function when a client (peripheral driver) of the SPB controller sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a> request to a target device that is attached to the bus. The <i>Request</i> parameter value is a handle that encapsulates this request.

An <i>EvtSpbControllerIoSequence</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the sequence operation in the completion status for the I/O request.

An <i>EvtSpbControllerIoSequence</i> callback is asynchronous. That is, the callback function should initiate the requested sequence (or the first part of the sequence) operation and then return without waiting for the operation to complete. Later, the SPB controller driver continues processing the request or completes it during interrupt DPCs or timer DPCs.

The SPB controller driver can retrieve the parameter values from the I/O request to determine the maximum length of the transfers within the sequence.  The driver can use this length to allocate DMA resources that it can reuse for each transfer within the sequence.

The SPB controller driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a> method to retrieve the control parameters and data buffer for each transfer in the sequence.  The buffer is a WDFMEMORY object that, in the current implementation, encapsulates a chained MDL. For more information about chained MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

The SPB controller should keep the target device selected for the entire sequence operation. If the target is selected by a device-select line, the line can be asserted continuously from the start of the first transfer in the sequence until the last transfer ends. This line can be asserted as early as the lock operation at the start of the sequence and can remain asserted until the unlock operation at the end of the sequence.

An optional delay can be specified for each transfer in a sequence.  The SPB controller driver is responsible for delaying at least that number of microseconds before starting the transfer.  If the first transfer in the sequence has an associated delay, the driver should first transmit the address or assert the device-select line of the target device, and then delay for the specified time before starting the data transfer.  During this delay, the target should remain selected  but the controller should not run the clock on the bus.

If the target device signals a NACK during a transfer in a sequence, the SPB controller stops the sequence.  (That is, the controller does not retry the failing transfer and does not try to perform the remaining transfers in the sequence.) If this occurs, the SPB controller driver should set the completion status of the I/O request to STATUS_SUCCESS, set the <b>Information</b> field in the I/O status block to the number of bytes actually transferred (not counting the data lost in the transfer that received the NACK), and complete the request.

The SPB controller driver should complete the I/O request with an error status code only if one of the following conditions occurs:

<ul>
<li>The SPB controller cannot select the target device (for example, a target device on an I²C bus signals a NACK when the controller transmits the address byte).</li>
<li>The SPB controller driver gets an error status  from a call to a WDF or WDM service while processing the sequence operation.</li>
</ul>
To register an <i>EvtSpbControllerIoSequence</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.


#### Examples

To define an <i>EvtSpbControllerIoSequence</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbControllerIoSequence</i> callback function that is named <code>MyEvtSpbControllerIoSequence</code>, use the EVT_SPB_CONTROLLER_SEQUENCE function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SPB_CONTROLLER_SEQUENCE  MyEvtSpbControllerIoSequence;</pre>
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
  MyEvtSpbControllerIoSequence(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST Request,
    ULONG TransferCount
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The EVT_SPB_CONTROLLER_SEQUENCE function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_SEQUENCE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a>
 

 

