---
UID: NC:sercx.EVT_SERCX_FILECLOSE
title: EVT_SERCX_FILECLOSE
author: windows-driver-content
description: The EvtSerCxFileClose event callback function notifies the serial controller driver that the file object that represents the serial controller device has been released.
old-location: serports\evtsercxfileclose.htm
old-project: serports
ms.assetid: C72CA6D0-DD85-46AC-9CE3-BE11233475C0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
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
req.alt-api: EvtSerCxFileClose
req.alt-loc: 1.0\Sercx.h
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
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX_FILECLOSE callback



## -description
The <i>EvtSerCxFileClose</i> event callback function notifies the serial controller driver that the file object that represents the serial controller device has been released.



## -prototype

````
EVT_SERCX_FILECLOSE EvtSerCxFileClose;

VOID EvtSerCxFileClose(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns
None.


## -remarks
This function should remove the serial controller device from the state in which it is ready to receive and transmit data. This function should disable interrupts if interrupts are enabled. Any memory that is allocated only for the lifetime of the file object should be deallocated either in this function or in the <a href="..\sercx\nc-sercx-evt_sercx_filecleanup.md">EvtSerCxFileCleanup</a> function.

If the serial controller driver implements an <i>EvtSerCxFileCleanup</i> function, the serial framework extension (SerCx)  calls this function before it calls the <i>EvtSerCxFileClose</i> function. SerCx calls the <i>EvtSerCxFileCleanup</i> function when a client closes the last handle to the file object that represents the serial controller device. After this call, the driver receives no new requests for I/O operations. SerCx calls the <i>EvtSerCxFileClose</i> function when the file object is released, which occurs only after all outstanding I/O requests are either completed or canceled.

To register an <i>EvtSerCxFileClose</i> callback function, the driver must call the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

The function type for this callback is declared in Sercx.h, as follows.

To define an <i>EvtSerCxFileClose</i> callback function that is named <code>MyEvtSerCxFileClose</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

Then, implement your callback function as follows.

For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.


## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx_filecleanup.md">EvtSerCxFileCleanup</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_FILECLOSE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

