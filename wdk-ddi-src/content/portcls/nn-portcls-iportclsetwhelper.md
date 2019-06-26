---
UID: NN:portcls.IPortClsEtwHelper
title: IPortClsEtwHelper (portcls.h)
description: The IPortClsEtwHelper interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions.
old-location: audio\iportclsetwhelper.htm
tech.root: audio
ms.assetid: 7BF9E3AB-D508-4FB8-8C47-C0B338933A56
ms.date: 05/08/2018
ms.keywords: IPortClsEtwHelper, IPortClsEtwHelper interface [Audio Devices], IPortClsEtwHelper interface [Audio Devices],described, audio.iportclsetwhelper, portcls/IPortClsEtwHelper
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IPortClsEtwHelper
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsEtwHelper interface


## -description


The <code>IPortClsEtwHelper</code> interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions.

The miniport driver uses the information from the helper functions to report glitching errors.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsEtwHelper</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortClsEtwHelper</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortClsEtwHelper</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsetwhelper-miniportwriteetwevent">MiniportWriteEtwEvent</a>
</td>
<td align="left" width="63%">
The <code>MiniportWriteEtwEvent</code> method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/glitch-reporting-for-offloaded-audio">Glitch Reporting for Offloaded Audio</a>
 

 

