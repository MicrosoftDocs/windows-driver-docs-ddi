---
UID: NC:spbcx.EVT_SPB_CONTROLLER_READ
title: EVT_SPB_CONTROLLER_READ (spbcx.h)
description: An SPB controller driver's EvtSpbControllerIoRead event callback function reads data from the specified target device into the buffers that are supplied with the read request.
old-location: spb\evtspbcontrollerioread.htm
tech.root: SPB
ms.assetid: 2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43
ms.date: 04/30/2018
ms.keywords: EVT_SPB_CONTROLLER_READ, EVT_SPB_CONTROLLER_READ callback, EvtSpbControllerIoRead, EvtSpbControllerIoRead callback function [Buses], SPB.evtspbcontrollerioread, spbcx/EvtSpbControllerIoRead
f1_keywords:
 - "spbcx/EvtSpbControllerIoRead"
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
- EvtSpbControllerIoRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SPB_CONTROLLER_READ callback function


## -description


An SPB controller driver's <i>EvtSpbControllerIoRead</i> event callback function reads data from the specified target device into the buffers that are supplied with the read request.


## -parameters




### -param Controller [in]

A WDFDEVICE handle to the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-device-object">framework device object</a> that represents the SPB controller.


### -param Target [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> callback that opened the connection to the target.


### -param Request [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.


### -param Length [in]

The number of bytes to read from the target device.


## -remarks



SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's <i>EvtSpbControllerIoRead</i> callback function when a client (peripheral driver) of the SPB controller sends an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> request to a target device that is attached to the bus. The <i>Request</i> parameter value is a handle that encapsulates this request.

An <i>EvtSpbControllerIoRead</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the read operation in the completion status for the I/O request.

An <i>EvtSpbControllerIoRead</i> callback is asynchronous.  That is, the callback function should initiate the requested read operation and then return without waiting for the operation to complete. Later, the SPB controller driver completes the read request during an interrupt DPC or a timer DPC.

If the read operation completes in full, the SPB controller driver should set the completion status to  STATUS_SUCCESS. If the target device indicates that it can supply some but not all  of the data requested, the SPB controller driver should retrieve as much data as is available, specify the number of data bytes retrieved, and set the completion status in the I/O request to  STATUS_SUCCESS. Such a partially completed read operation cannot occur on an SPI or I²C bus, but might occur on another type of bus.

If the read operation fails due to line noise, a controller hardware error, or a driver error, then the SPB controller driver should set the completion status in the I/O request to an appropriate error code. Not all buses provide a mechanism for a target device to report a transport error or a partially completed transfer, and not all controllers can detect these conditions.

To register an <i>EvtSpbControllerIoRead</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a> method.


#### Examples

To define an <i>EvtSpbControllerIoRead</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSpbControllerIoRead</i> callback function that is named <code>MyEvtSpbControllerIoRead</code>, use the EVT_SPB_CONTROLLER_READ function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SPB_CONTROLLER_READ  MyEvtSpbControllerIoRead;</pre>
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
  MyEvtSpbControllerIoRead(
    WDFDEVICE Controller,
    SPBTARGET Target,
    SPBREQUEST Request,
    size_t Length
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The EVT_SPB_CONTROLLER_READ function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_READ function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_controller_sequence">EvtSpbControllerIoSequence</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbdeviceinitialize">SpbDeviceInitialize</a>
 

 

