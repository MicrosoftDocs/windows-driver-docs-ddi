---
UID: NC:sercx.EVT_SERCX_RECEIVE_CANCEL
title: EVT_SERCX_RECEIVE_CANCEL
author: windows-driver-content
description: The EvtSerCxReceiveCancel event callback function notifies the serial controller driver that the pending receive request is canceled.
old-location: serports\evtsercxreceivecancel.htm
old-project: serports
ms.assetid: 17362701-67C9-4275-B072-CB17111A838F
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 1/EvtSerCxReceiveCancel, EVT_SERCX_RECEIVE_CANCEL, EVT_SERCX_RECEIVE_CANCEL callback, EvtSerCxReceiveCancel, EvtSerCxReceiveCancel callback function [Serial Ports], serports.evtsercxreceivecancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	1.0\Sercx.h
api_name:
-	EvtSerCxReceiveCancel
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX_RECEIVE_CANCEL callback function


## -description


The <i>EvtSerCxReceiveCancel</i> event callback function notifies the serial controller driver that the pending receive request is canceled.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



None.




## -remarks



The serial framework extension (SerCx) calls this function to inform the serial controller driver that the current receive request has been canceled.  If the driver has an outstanding receive operation in progress, the driver should cancel this operation and call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406713">SerCxProgressReceive</a> method to report the cancellation. In the <b>SerCxProgressReceive</b> call, set <i>BytesReceived</i> to the number of bytes received before the operation was canceled, and set <i>ReceiveStatus</i> to <b>SerCxStatusCancelled</b>.

To register an <i>EvtSerCxReceiveCancel</i> callback function, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
  EVT_SERCX_RECEIVE_CANCEL(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxReceiveCancel</i> callback function that is named <code>MyEvtSerCxReceiveCancel</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_RECEIVE_CANCEL MyEvtSerCxReceiveCancel;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  MyEvtSerCxReceiveCancel(
    __in WDFDEVICE Device
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406713">SerCxProgressReceive</a>
 

 

