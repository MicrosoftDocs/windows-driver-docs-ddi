---
UID: NN:wdtfinterfaces.IWDTFSimpleIOStressActions2
title: IWDTFSimpleIOStressActions2 (wdtfinterfaces.h)
description: Defines operations for a collection of simple asynchronous I/O functionality tests.
old-location: dtf\iwdtfsimpleiostressactions2.htm
tech.root: dtf
ms.assetid: d50bf1d1-fa36-4ab1-9173-bdaf2f5a9f28
ms.date: 03/29/2018
ms.keywords: IWDTFSimpleIOStressActions2, IWDTFSimpleIOStressActions2 interface [Windows Device Testing Framework], IWDTFSimpleIOStressActions2 interface [Windows Device Testing Framework], described, dtf.iwdtfsimpleiostressactions2, wdtfinterfaces/IWDTFSimpleIOStressActions2
ms.topic: interface
req.header: wdtfinterfaces.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl: WDTFInterfaces.idl
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wdtfinterfaces.h
api_name:
- IWDTFSimpleIOStressActions2
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimpleIOStressActions2 interface


## -description


Defines operations for a collection of simple asynchronous I/O functionality tests.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSimpleIOStressActions2</b> interface inherits from <b>IWDTFSimpleIOStressActionsBase2</b>. <b>IWDTFSimpleIOStressActions2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFSimpleIOStressActions2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Continue</a>
</td>
<td align="left" width="63%">
Continues the I/O.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">ContinueAsync</a>
</td>
<td align="left" width="63%">
Asynchronously signals the I/O to continue.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Pause</a>
</td>
<td align="left" width="63%">
Pauses the I/O.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaasyncoperation-start">Start</a>
</td>
<td align="left" width="63%">
Opens the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfinterfaces/nf-wdtfinterfaces-iwdtfsimpleiostressaction2-startasync">StartAsync</a>
</td>
<td align="left" width="63%">
Asynchronously signals a start event to occur.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/test/wpt/stop-icontrolmanager">Stop</a>
</td>
<td align="left" width="63%">
Stops the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">StopAsync</a>
</td>
<td align="left" width="63%">
Asynchronously signals the stop event to occur.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">WaitAsyncCompletion</a>
</td>
<td align="left" width="63%">
Waits for the completion of any of the asynchronous events.

</td>
</tr>
</table> 

