---
UID: NN:wdtfinterfaces.IWDTFSimpleIOEx2
title: IWDTFSimpleIOEx2 (wdtfinterfaces.h)
description: Defines operations for a simple synchronous I/O functionality test.
old-location: dtf\iwdtfsimpleioex2.htm
tech.root: dtf
ms.assetid: a916e6b1-692c-47e9-83cc-3aeae80fb624
ms.date: 04/04/2018
ms.keywords: IWDTFSimpleIOEx2, IWDTFSimpleIOEx2 interface [Windows Device Testing Framework], IWDTFSimpleIOEx2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFSimpleIOEx2, dtf.iwdtfsimpleioex2, wdtfinterfaces/IWDTFSimpleIOEx2
ms.topic: interface
f1_keywords:
 - "wdtfinterfaces/IWDTFSimpleIOEx2"
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
- IWDTFSimpleIOEx2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimpleIOEx2 interface


## -description


Defines operations for a simple synchronous I/O functionality test.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSimpleIOEx2</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFSimpleIOEx2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFSimpleIOEx2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfinterfaces/nf-wdtfinterfaces-iwdtfsimpleioex2-close">Close</a>
</td>
<td align="left" width="63%">
Closes the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfinterfaces/nf-wdtfinterfaces-iwdtfsimpleioex2-open">Open</a>
</td>
<td align="left" width="63%">
Opens the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfinterfaces/nf-wdtfinterfaces-iwdtfsimpleioex2-performio">PerformIO</a>
</td>
<td align="left" width="63%">
Performs a small amount of simple I/O to the device.

</td>
</tr>
</table> 


## -remarks



The <b>IWDTFSimpleIOEx2</b> action interface acts on an instance of the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface that is retrieved by querying the 
device depot. You can retrieve a target-specific implementation of an action interface by calling the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a> method with the 
desired WDTF <i>ProgID.</i>

For an asynchronous interface for this same underlying functionality, 
see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfinterfaces/nn-wdtfinterfaces-iwdtfsimpleiostressaction2">IWDTFSimpleIOStressAction2</a>. 

The <b>IWDTFSimpleIOEx2</b> action interface is compatible with the following device 
classes:

<ul>
<li>
CD-ROM drives (class =CDROM) 

</li>
<li>
Display adapters (class = Display)

</li>
<li>
Multimedia devices (class = Media)

</li>
<li>
Network adapters (class = Net)

</li>
<li>
Storage volumes (class = Volume)

</li>
</ul>
For more information about device classes, see 
<a href="https://docs.microsoft.com/windows/desktop/api/setupapi/ns-setupapi-_sp_devinfo_data">Device Setup Classes</a>.

To learn more about the specifics of how the <b>IWDTFSimpleIOEx2</b> action 
interface works, or to support additional device classes, try to implement a target-specific version 
of it for your device class. For more information about how to implement such a version, see 
<a href="https://docs.microsoft.com/windows-hardware/drivers/wdtf/wdtf-overview">Windows Device Testing Framework 
Design Guide</a>.

<div class="alert"><b>Note</b>  The implementations of this interface are not thread-safe.</div>
<div> </div>


