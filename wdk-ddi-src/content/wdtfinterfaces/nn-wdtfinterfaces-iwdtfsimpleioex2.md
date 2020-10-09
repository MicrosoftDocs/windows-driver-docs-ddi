---
UID: NN:wdtfinterfaces.IWDTFSimpleIOEx2
title: IWDTFSimpleIOEx2 (wdtfinterfaces.h)
description: Defines operations for a simple synchronous I/O functionality test.
old-location: dtf\iwdtfsimpleioex2.htm
tech.root: dtf
ms.assetid: a916e6b1-692c-47e9-83cc-3aeae80fb624
ms.date: 04/04/2018
keywords: ["IWDTFSimpleIOEx2 interface"]
ms.keywords: IWDTFSimpleIOEx2, IWDTFSimpleIOEx2 interface [Windows Device Testing Framework], IWDTFSimpleIOEx2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFSimpleIOEx2, dtf.iwdtfsimpleioex2, wdtfinterfaces/IWDTFSimpleIOEx2
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFSimpleIOEx2
 - wdtfinterfaces/IWDTFSimpleIOEx2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFInterfaces.Interop.dll
api_name:
 - IWDTFSimpleIOEx2
---

# IWDTFSimpleIOEx2 interface


## -description

Defines operations for a simple synchronous I/O functionality test.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSimpleIOEx2</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFSimpleIOEx2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

The <b>IWDTFSimpleIOEx2</b> action interface acts on an instance of the 
<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface that is retrieved by querying the 
device depot. You can retrieve a target-specific implementation of an action interface by calling the 
<a href="/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a> method with the 
desired WDTF <i>ProgID.</i>

For an asynchronous interface for this same underlying functionality, 
see <a href="/windows-hardware/drivers/ddi/wdtfinterfaces/nn-wdtfinterfaces-iwdtfsimpleiostressaction2">IWDTFSimpleIOStressAction2</a>. 

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
<a href="/windows/win32/api/setupapi/ns-setupapi-sp_devinfo_data">Device Setup Classes</a>.

To learn more about the specifics of how the <b>IWDTFSimpleIOEx2</b> action 
interface works, or to support additional device classes, try to implement a target-specific version 
of it for your device class. For more information about how to implement such a version, see 
<a href="/windows-hardware/drivers/wdtf/wdtf-overview">Windows Device Testing Framework 
Design Guide</a>.

<div class="alert"><b>Note</b>  The implementations of this interface are not thread-safe.</div>
<div> </div>