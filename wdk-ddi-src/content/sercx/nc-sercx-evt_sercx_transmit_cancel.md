---
UID: NC:sercx.EVT_SERCX_TRANSMIT_CANCEL
title: EVT_SERCX_TRANSMIT_CANCEL (sercx.h)
description: The EvtSerCxTransmitCancel event callback function notifies the serial controller driver that the pending transmit request is canceled.
old-location: serports\evtsercxtransmitcancel.htm
tech.root: serports
ms.assetid: 7922A3BD-8829-42A3-9F94-3C26F1262626
ms.date: 04/23/2018
keywords: ["EVT_SERCX_TRANSMIT_CANCEL callback function"]
ms.keywords: 1/EvtSerCxTransmitCancel, EVT_SERCX_TRANSMIT_CANCEL, EVT_SERCX_TRANSMIT_CANCEL callback, EvtSerCxTransmitCancel, EvtSerCxTransmitCancel callback function [Serial Ports], serports.evtsercxtransmitcancel
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX_TRANSMIT_CANCEL
 - sercx/EVT_SERCX_TRANSMIT_CANCEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 1.0\Sercx.h
api_name:
 - EvtSerCxTransmitCancel
---

# EVT_SERCX_TRANSMIT_CANCEL callback function


## -description

The <i>EvtSerCxTransmitCancel</i> event callback function notifies the serial controller driver that the pending transmit request is canceled.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.

## -remarks

The serial framework extension (SerCx) calls this function to inform the serial controller driver that the current transmit request has been canceled.  If the driver has an outstanding transmit operation in progress, the driver should cancel this operation and call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogresstransmit">SerCxProgressTransmit</a> method to report the cancellation. In the <b>SerCxProgressTransmit</b> call, set <i>BytesTransmitted</i> to the number of bytes transmitted before the operation was canceled, and set <i>TransmitStatus</i> to <b>SerCxStatusCancelled</b>.

To register an <i>EvtSerCxTransmitCancel</i> callback function, the driver must call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.


```cpp
typedef VOID
  EVT_SERCX_TRANSMIT_CANCEL(
    __in WDFDEVICE Device
    );
```

To define an <i>EvtSerCxTransmitCancel</i> callback function that is named <code>MyEvtSerCxTransmitCancel</code>, you must first provide a function declaration that <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.


```cpp
EVT_SERCX_TRANSMIT_CANCEL MyEvtSerCxTransmitCancel;
```

Then, implement your callback function as follows.


```cpp
VOID
  MyEvtSerCxTransmitCancel(
    __in WDFDEVICE Device
    )
{ ... }
```

For more information about SDV requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>