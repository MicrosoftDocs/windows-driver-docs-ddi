---
UID: NC:sercx.EVT_SERCX_RECEIVE_CANCEL
title: EVT_SERCX_RECEIVE_CANCEL
author: windows-driver-content
description: The EvtSerCxReceiveCancel event callback function notifies the serial controller driver that the pending receive request is canceled.
old-location: serports\evtsercxreceivecancel.htm
old-project: serports
ms.assetid: 17362701-67C9-4275-B072-CB17111A838F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxreceivecancel, EvtSerCxReceiveCancel callback function [Serial Ports], EvtSerCxReceiveCancel, EVT_SERCX_RECEIVE_CANCEL, EVT_SERCX_RECEIVE_CANCEL, 1/EvtSerCxReceiveCancel
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
-	EvtSerCxReceiveCancel
product: Windows
targetos: Windows
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX_RECEIVE_CANCEL callback


## -description


The <i>EvtSerCxReceiveCancel</i> event callback function notifies the serial controller driver that the pending receive request is canceled.


## -prototype


````
EVT_SERCX_RECEIVE_CANCEL EvtSerCxReceiveCancel;

VOID EvtSerCxReceiveCancel(
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


The serial framework extension (SerCx) calls this function to inform the serial controller driver that the current receive request has been canceled.  If the driver has an outstanding receive operation in progress, the driver should cancel this operation and call the <a href="..\sercx\nf-sercx-sercxprogressreceive.md">SerCxProgressReceive</a> method to report the cancellation. In the <b>SerCxProgressReceive</b> call, set <i>BytesReceived</i> to the number of bytes received before the operation was canceled, and set <i>ReceiveStatus</i> to <b>SerCxStatusCancelled</b>.

To register an <i>EvtSerCxReceiveCancel</i> callback function, the driver must call the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method.



## -see-also

<a href="..\sercx\nf-sercx-sercxprogressreceive.md">SerCxProgressReceive</a>

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_RECEIVE_CANCEL callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

