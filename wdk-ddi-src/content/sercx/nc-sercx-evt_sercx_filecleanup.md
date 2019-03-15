---
UID: NC:sercx.EVT_SERCX_FILECLEANUP
title: EVT_SERCX_FILECLEANUP (sercx.h)
description: The EvtSerCxFileCleanup event callback function notifies the serial controller driver that a client has closed the last handle to the file object that represents the serial controller device.
old-location: serports\evtsercxfilecleanup.htm
tech.root: serports
ms.assetid: D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC
ms.date: 04/23/2018
ms.keywords: 1/EvtSerCxFileCleanup, EVT_SERCX_FILECLEANUP, EVT_SERCX_FILECLEANUP callback, EvtSerCxFileCleanup, EvtSerCxFileCleanup callback function [Serial Ports], serports.evtsercxfilecleanup
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 1.0\Sercx.h
api_name:
- EvtSerCxFileCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX_FILECLEANUP callback function


## -description


The <i>EvtSerCxFileCleanup</i> event callback function notifies the serial controller driver that a client has closed the last handle to the file object that represents the serial controller device.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



None.




## -remarks



This function can deallocate certain system resources that the driver previously allocated for the lifetime of the file object. In conjunction with the <a href="https://msdn.microsoft.com/C72CA6D0-DD85-46AC-9CE3-BE11233475C0">EvtSerCxFileClose</a> function, the <i>EvtSerCxFileCleanup</i> function should remove the serial controller device from the state in which it is ready to receive and transmit data. The <i>EvtSerCxFileCleanup</i> function should focus specifically on clean-up tasks, such as deallocating memory.

If the serial controller driver previously allocated memory only for the lifetime of the file object that is now closed, the driver should deallocate this memory in either the <i>EvtSerCxFileCleanup</i> or <i>EvtSerCxFileClose</i> function.

Typically, interrupts should be disabled only after the file object is released. Thus, the <i>EvtSerCxFileClose</i> function, and not the <i>EvtSerCxFileCleanup</i> function, should disable the interrupts.

SerCx calls a driver's <i>EvtSerCxFileCleanup</i> function after the last handle to the file object is closed. Because of outstanding I/O requests, this object might not yet be released. After this call, the driver receives no new requests for I/O operations.

SerCx calls a driver's <i>EvtSerCxFileClose</i> function after it calls the driver's <i>EvtSerCxFileCleanup</i> function. SerCx calls the <i>EvtSerCxFileClose</i> function after the file object is released, which occurs only when all outstanding I/O requests are either completed or canceled.

The <i>EvtSerCxFileCleanup</i> function is optional. If a serial controller driver does not implement this function, the driver's <i>EvtSerCxFileClose</i> function must handle all clean-up tasks that are required after the last file handle is closed.

To register an <i>EvtSerCxFileCleanup</i> callback function, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
  EVT_SERCX_FILECLEANUP(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxFileCleanup</i> callback function that is named <code>MyEvtSerCxFileCleanup</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_FILECLEANUP MyEvtSerCxFileCleanup;</pre>
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
  MyEvtSerCxFileCleanup(
    __in WDFDEVICE Device
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/C72CA6D0-DD85-46AC-9CE3-BE11233475C0">EvtSerCxFileClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a>
 

 

