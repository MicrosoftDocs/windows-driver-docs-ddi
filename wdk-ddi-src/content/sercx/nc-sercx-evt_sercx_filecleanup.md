---
UID: NC:sercx.EVT_SERCX_FILECLEANUP
title: EVT_SERCX_FILECLEANUP
author: windows-driver-content
description: The EvtSerCxFileCleanup event callback function notifies the serial controller driver that a client has closed the last handle to the file object that represents the serial controller device.
old-location: serports\evtsercxfilecleanup.htm
old-project: serports
ms.assetid: D9E19BD1-2C44-4F86-9AEB-F50443FAE8DC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxfilecleanup, EvtSerCxFileCleanup callback function [Serial Ports], EvtSerCxFileCleanup, EVT_SERCX_FILECLEANUP, EVT_SERCX_FILECLEANUP, 1/EvtSerCxFileCleanup
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	1.0\Sercx.h
apiname: 
-	EvtSerCxFileCleanup
product: Windows
targetos: Windows
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX_FILECLEANUP callback


## -description


The <i>EvtSerCxFileCleanup</i> event callback function notifies the serial controller driver that a client has closed the last handle to the file object that represents the serial controller device.


## -prototype


````
EVT_SERCX_FILECLEANUP EvtSerCxFileCleanup;

VOID EvtSerCxFileCleanup(
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


This function can deallocate certain system resources that the driver previously allocated for the lifetime of the file object. In conjunction with the <a href="..\sercx\nc-sercx-evt_sercx_fileclose.md">EvtSerCxFileClose</a> function, the <i>EvtSerCxFileCleanup</i> function should remove the serial controller device from the state in which it is ready to receive and transmit data. The <i>EvtSerCxFileCleanup</i> function should focus specifically on clean-up tasks, such as deallocating memory.

If the serial controller driver previously allocated memory only for the lifetime of the file object that is now closed, the driver should deallocate this memory in either the <i>EvtSerCxFileCleanup</i> or <i>EvtSerCxFileClose</i> function.

Typically, interrupts should be disabled only after the file object is released. Thus, the <i>EvtSerCxFileClose</i> function, and not the <i>EvtSerCxFileCleanup</i> function, should disable the interrupts.

SerCx calls a driver's <i>EvtSerCxFileCleanup</i> function after the last handle to the file object is closed. Because of outstanding I/O requests, this object might not yet be released. After this call, the driver receives no new requests for I/O operations.

SerCx calls a driver's <i>EvtSerCxFileClose</i> function after it calls the driver's <i>EvtSerCxFileCleanup</i> function. SerCx calls the <i>EvtSerCxFileClose</i> function after the file object is released, which occurs only when all outstanding I/O requests are either completed or canceled.

The <i>EvtSerCxFileCleanup</i> function is optional. If a serial controller driver does not implement this function, the driver's <i>EvtSerCxFileClose</i> function must handle all clean-up tasks that are required after the last file handle is closed.

To register an <i>EvtSerCxFileCleanup</i> callback function, the driver must call the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx_fileclose.md">EvtSerCxFileClose</a>

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_FILECLEANUP callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

