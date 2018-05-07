---
UID: NN:dsound.IKsPropertySet
title: IKsPropertySet
author: windows-driver-content
description: The IKsPropertySet interface provides methods that access properties of KS objects that are implemented in a KS minidriver.
old-location: stream\ikspropertyset.htm
old-project: stream
ms.assetid: 9999d6ec-977c-4425-ad38-0c5478272c76
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IKsPropertySet, IKsPropertySet interface [Streaming Media Devices], IKsPropertySet interface [Streaming Media Devices],described, dsound/IKsPropertySet, ksproxy_5f6316c6-5bcf-4155-b4a5-976a0cee8aa5.xml, stream.ikspropertyset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dsound.h
req.include-header: Ksproxy.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dsound.h
api_name:
-	IKsPropertySet
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPropertySet interface


## -description


The <b>IKsPropertySet</b> interface provides methods that access properties of KS objects that are implemented in a KS minidriver.

The IID for this interface is IID_IKsPropertySet.
<div class="alert"><b>Note</b>    Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.<p class="note">If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.

</div><div> </div>

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPropertySet</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsPropertySet</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsPropertySet</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a>
</td>
<td align="left" width="63%">
Retrieves a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8b59da4f-0beb-46e8-913d-b992fa9f694d">QuerySupported</a>
</td>
<td align="left" width="63%">
Determines the support of a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544503">Set</a>
</td>
<td align="left" width="63%">
Sets a property.

</td>
</tr>
</table> 


## -remarks



The <b>IKsPropertySet</b> interface methods translate user-mode property requests into kernel-mode property sets that are used by KS minidrivers. 

KS objects include, for example, KS filters, KS pins, and KS clocks. 



