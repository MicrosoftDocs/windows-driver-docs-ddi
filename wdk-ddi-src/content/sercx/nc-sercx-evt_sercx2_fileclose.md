---
UID: NC:sercx.EVT_SERCX2_FILECLOSE
title: EVT_SERCX2_FILECLOSE
author: windows-driver-content
description: The EvtSerCx2FileClose event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that the client released the file object that represents the logical connection to the serial controller device.
old-location: serports\evtsercx2fileclose.htm
old-project: serports
ms.assetid: C923D37B-595F-41CF-B2F3-F12303120C95
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2fileclose, EvtSerCx2FileClose callback function [Serial Ports], EvtSerCx2FileClose, EVT_SERCX2_FILECLOSE, EVT_SERCX2_FILECLOSE, 2/EvtSerCx2FileClose
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
-	EvtSerCx2FileClose
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_FILECLOSE callback


## -description


The <i>EvtSerCx2FileClose</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to notify the serial controller driver that the client released the file object that represents the logical connection to the serial controller device.


## -prototype


````
EVT_SERCX2_FILECLOSE EvtSerCx2FileClose;

VOID EvtSerCx2FileClose(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters




#### - Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers this function in the call to the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_FILECLOSE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

