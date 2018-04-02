---
UID: NC:sercx.EVT_SERCX2_PURGE_FIFOS
title: EVT_SERCX2_PURGE_FIFOS
author: windows-driver-content
description: The EvtSerCx2PurgeFifos event callback function is called by version 2 of the serial framework extension (SerCx2) to purge the FIFO buffers in the serial controller hardware.
old-location: serports\evtsercx2purgefifos.htm
old-project: serports
ms.assetid: 52875B36-F52B-4D29-9C9D-76DB12BFEEA6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/EvtSerCx2PurgeFifos, EVT_SERCX2_PURGE_FIFOS, EvtSerCx2PurgeFifos, EvtSerCx2PurgeFifos callback function [Serial Ports], serports.evtsercx2purgefifos
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
-	2.0\Sercx.h
api_name:
-	EvtSerCx2PurgeFifos
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PURGE_FIFOS callback


## -description


The <i>EvtSerCx2PurgeFifos</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to purge the FIFO buffers in the serial controller hardware.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>.


### -param PurgeRxFifo [in]

Whether to purge the receive FIFO. If this parameter is set to <b>TRUE</b>, purge the receive FIFO. If <b>FALSE</b>, do not purge the receive FIFO.


### -param PurgeTxFifo [in]

Whether to purge the transmit FIFO. If this parameter is set to <b>TRUE</b>, purge the transmit FIFO. If <b>FALSE</b>, do not purge the transmit FIFO.


## -returns



None.




## -remarks



Your serial controller driver must implement this function. The driver registers the function in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

SerCx2 calls the <i>EvtSerCx2PurgeFifos</i> function when a client (peripheral driver) sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546655">IOCTL_SERIAL_PURGE</a> control request that requires either one or both of the FIFO buffers in the serial controller hardware to be purged. If the <b>IOCTL_SERIAL_PURGE</b> control request requires pending read or write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) requests to be canceled, SerCx2 cancels these requests before it calls the <i>EvtSerCx2PurgeFifos</i> function.

SerCx2 also calls the <i>EvtSerCx2PurgeFifos</i> function when a client opens a logical connection to the serial controller device and obtains a file handle to this connection. For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

To define an <i>EvtSerCx2PurgeFifos</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PurgeFifos</i> callback function that is named <code>MyPurgeFifos</code>, use the <b>EVT_SERCX2_PURGE_FIFOS</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PURGE_FIFOS  MyPurgeFifos;</pre>
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
  MyPurgeFifos(
    WDFDEVICE  Device,
    BOOLEAN PurgeRxFifo,
    BOOLEAN PurgeTxFifo
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PURGE_FIFOS</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PURGE_FIFOS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546655">IOCTL_SERIAL_PURGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>
 

 

