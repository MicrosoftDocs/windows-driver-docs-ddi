---
UID: NC:sercx.EVT_SERCX2_FILEOPEN
title: EVT_SERCX2_FILEOPEN
author: windows-driver-content
description: The EvtSerCx2FileOpen event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that a client opened a logical connection to the serial controller device and that a file object has been created to represent this connection.
old-location: serports\evtsercx2fileopen.htm
old-project: serports
ms.assetid: A8E6EB7F-B6FE-4FA1-88A4-52C584E69D5B
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2fileopen, EvtSerCx2FileOpen callback function [Serial Ports], EvtSerCx2FileOpen, EVT_SERCX2_FILEOPEN, EVT_SERCX2_FILEOPEN, 2/EvtSerCx2FileOpen
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	2.0\Sercx.h
apiname: 
-	EvtSerCx2FileOpen
product: Windows
targetos: Windows
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_FILEOPEN callback


## -description


The <i>EvtSerCx2FileOpen</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that a client opened a logical connection to the serial controller device and that a file object has been created to represent this connection.


## -prototype


````
EVT_SERCX2_FILEOPEN EvtSerCx2FileOpen;

NTSTATUS EvtSerCx2FileOpen(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.


## -returns


The <i>EvtSerCx2FileOpen</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers this function in the call to the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller. SerCx2 calls the <i>EvtSerCx2FileOpen</i> function when a client driver opens a file handle to the serial controller driver stack.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_FILEOPEN callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

