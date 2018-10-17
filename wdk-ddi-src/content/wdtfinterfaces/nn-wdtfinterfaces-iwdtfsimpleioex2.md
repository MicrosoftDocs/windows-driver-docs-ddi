---
UID: NN:wdtfinterfaces.IWDTFSimpleIOEx2
title: IWDTFSimpleIOEx2
author: windows-driver-content
description: Defines operations for a simple synchronous I/O functionality test.
old-location: dtf\iwdtfsimpleioex2.htm
tech.root: dtf
ms.assetid: a916e6b1-692c-47e9-83cc-3aeae80fb624
ms.date: 4/4/2018
ms.keywords: IWDTFSimpleIOEx2, IWDTFSimpleIOEx2 interface [Windows Device Testing Framework], IWDTFSimpleIOEx2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFSimpleIOEx2, dtf.iwdtfsimpleioex2, wdtfinterfaces/IWDTFSimpleIOEx2
ms.topic: interface
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFInterfaces.Interop.dll
api_name:
-	IWDTFSimpleIOEx2
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451151">Close</a>
</td>
<td align="left" width="63%">
Closes the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451153">Open</a>
</td>
<td align="left" width="63%">
Opens the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451155">PerformIO</a>
</td>
<td align="left" width="63%">
Performs a small amount of simple I/O to the device.

</td>
</tr>
</table> 


## -remarks



The <b>IWDTFSimpleIOEx2</b> action interface acts on an instance of the 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface that is retrieved by querying the 
device depot. You can retrieve a target-specific implementation of an action interface by calling the 
<a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a> method with the 
desired WDTF <i>ProgID.</i>

For an asynchronous interface for this same underlying functionality, 
see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451157">IWDTFSimpleIOStressAction2</a>. 

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552344">Device Setup Classes</a>.

To learn more about the specifics of how the <b>IWDTFSimpleIOEx2</b> action 
interface works, or to support additional device classes, try to implement a target-specific version 
of it for your device class. For more information about how to implement such a version, see 
<a href="https://msdn.microsoft.com/7e7660ec-1f17-4987-82c0-f62cca3a99b9">Windows Device Testing Framework 
Design Guide</a>.

<div class="alert"><b>Note</b>  The implementations of this interface are not thread-safe.</div>
<div> </div>


