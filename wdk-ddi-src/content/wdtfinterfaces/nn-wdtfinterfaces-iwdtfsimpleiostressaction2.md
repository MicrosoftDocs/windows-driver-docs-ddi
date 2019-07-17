---
UID: NN:wdtfinterfaces.IWDTFSimpleIOStressAction2
title: IWDTFSimpleIOStressAction2 (wdtfinterfaces.h)
description: Defines operations for a simple asynchronous I/O functionality test.
old-location: dtf\iwdtfsimpleiostressaction2.htm
tech.root: dtf
ms.assetid: dc594873-2347-4ad8-9748-2d5a1fa4d8a7
ms.date: 04/04/2018
ms.keywords: IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFSimpleIOStressAction2, dtf.iwdtfsimpleiostressaction2, wdtfinterfaces/IWDTFSimpleIOStressAction2
ms.topic: interface
f1_keywords:
 - "wdtfinterfaces/IWDTFSimpleIOStressAction2"
req.header: wdtfinterfaces.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFInterfaces.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFInterfaces.Interop.dll
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
- WDTFInterfaces.Interop.dll
api_name:
- IWDTFSimpleIOStressAction2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimpleIOStressAction2 interface


## -description


Defines operations for a simple asynchronous I/O functionality test.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSimpleIOStressAction2</b> interface inherits from <b>IWDTFActionWithCustomActions2</b>. <b>IWDTFSimpleIOStressAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFSimpleIOStressAction2</b> interface has these methods.
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

