---
UID: NC:sercx.EVT_SERCX_FILECLOSE
title: EVT_SERCX_FILECLOSE
author: windows-driver-content
description: The EvtSerCxFileClose event callback function notifies the serial controller driver that the file object that represents the serial controller device has been released.
old-location: serports\evtsercxfileclose.htm
tech.root: serports
ms.assetid: C72CA6D0-DD85-46AC-9CE3-BE11233475C0
ms.date: 04/23/2018
ms.keywords: 1/EvtSerCxFileClose, EVT_SERCX_FILECLOSE, EVT_SERCX_FILECLOSE callback, EvtSerCxFileClose, EvtSerCxFileClose callback function [Serial Ports], serports.evtsercxfileclose
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
-	EvtSerCxFileClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX_FILECLOSE callback function


## -description


The <i>EvtSerCxFileClose</i> event callback function notifies the serial controller driver that the file object that represents the serial controller device has been released.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns



None.




## -remarks



This function should remove the serial controller device from the state in which it is ready to receive and transmit data. This function should disable interrupts if interrupts are enabled. Any memory that is allocated only for the lifetime of the file object should be deallocated either in this function or in the <a href="https://msdn.microsoft.com/D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC">EvtSerCxFileCleanup</a> function.

If the serial controller driver implements an <i>EvtSerCxFileCleanup</i> function, the serial framework extension (SerCx)  calls this function before it calls the <i>EvtSerCxFileClose</i> function. SerCx calls the <i>EvtSerCxFileCleanup</i> function when a client closes the last handle to the file object that represents the serial controller device. After this call, the driver receives no new requests for I/O operations. SerCx calls the <i>EvtSerCxFileClose</i> function when the file object is released, which occurs only after all outstanding I/O requests are either completed or canceled.

To register an <i>EvtSerCxFileClose</i> callback function, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a> method.

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
  EVT_SERCX_FILECLOSE(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxFileClose</i> callback function that is named <code>MyEvtSerCxFileClose</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_FILECLOSE MyEvtSerCxFileClose;</pre>
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
  MyEvtSerCxFileClose(
    __in WDFDEVICE Device
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC">EvtSerCxFileCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406711">SerCxInitialize</a>
 

 

