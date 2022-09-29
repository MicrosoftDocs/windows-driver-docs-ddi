---
UID: NF:printerextension.IPrinterQueue.SendBidiQuery
title: IPrinterQueue::SendBidiQuery (printerextension.h)
description: Performs an asynchronous refresh operation with the specified query, and invokes the IPrinterQueueEvent::OnBidiResponseReceived method.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterQueue::SendBidiQuery"]
ms.keywords: IPrinterQueue, IPrinterQueue interface [Print Devices],SendBidiQuery method, IPrinterQueue.SendBidiQuery, IPrinterQueue::SendBidiQuery, SendBidiQuery, SendBidiQuery method [Print Devices], SendBidiQuery method [Print Devices],IPrinterQueue interface, print.iprinterqueue_sendbidiquery, printerextension/IPrinterQueue::SendBidiQuery
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrinterQueue::SendBidiQuery
 - printerextension/IPrinterQueue::SendBidiQuery
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueue::SendBidiQuery
---

## -description

Performs an asynchronous refresh operation with the specified query, and invokes the [IPrinterQueueEvent::OnBidiResponseReceived](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueevent-onbidiresponsereceived) method.

## -parameters

### -param bstrBidiQuery [in]

The specified query.

## -returns

This method returns an **HRESULT** value.

## -remarks

When the **SendBidiQuery** method is called, it immediately raises the [IPrinterQueueEvent::OnBidiResponseReceived](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueevent-onbidiresponsereceived) event, if there is a cached response available.  The print system then starts an asynchronous operation to use the [Bidi Communication Interfaces](/previous-versions/dd183365(v=vs.85)). At this point **SendBidiQuery** returns, thus unblocking the caller.  When the asynchronous operation completes, the print system raises the **IPrinterQueueEvent::OnBidiResponseReceived** event again. **SendBidiQuery** is decoupled from its associated response on purpose. The decoupling is done because, in the case where there is no cached data, the resulting latency can be due to many factors and an immediate response cannot be expected.  Additionally the caller may receive multiple responses based on whether there is cached data, and whether there is a response from the device.

Using the [Bidi Communication Interfaces](/previous-versions/dd183365(v=vs.85)) causes the port monitor to refresh the underlying requested values. In the case of USB, if a JavaScript component is available, then the JavaScript code is invoked to refresh the requested values.

The cache is also updated in the following situations:

- At predetermined intervals

  - For WSD devices the data is updated when the device reports changes via events.

  - For TCP & USB devices the refresh interval is based on where the Bidi value is defined.

  - All standard Bidi values (as defined by the port monitor's embedded Bidi files) are refreshed at an interval that is preset by the port monitors. If the specific Bidi Query is part of the IHV Bidi Extension, then the refresh interval is specified in the XML extension file for each individual value.

- When printer configuration changes

  - For example, when a WSD-based device raises an event to let the spooler (WSDMon) know that something about the device has changed. In other words, the printer configuration has changed.

## -see-also

[Bidi Communication Interfaces](/previous-versions/dd183365(v=vs.85))

[IPrinterQueue](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterqueue)

[IPrinterQueueEvent::OnBidiResponseReceived](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueevent-onbidiresponsereceived)
