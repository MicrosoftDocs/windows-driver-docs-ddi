---
UID: NN:filterpipeline.IPartDiscardControl
title: IPartDiscardControl
author: windows-driver-content
description: The filter pipeline supports the discard control.
old-location: print\ipartdiscardcontrol.htm
old-project: print
ms.assetid: 30c6fb0c-42ea-441f-b0a2-3310f8a5b407
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPartDiscardControl
req.alt-loc: filterpipeline.h
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
req.typenames: EXpsFontRestriction
---

# IPartDiscardControl interface



## -description
The filter pipeline supports the discard control. Filters can use this object, if they obtain it from <a href="https://msdn.microsoft.com/library/windows/hardware/ff556324">IXpsDocumentProvider::GetXpsPart</a> method. In some cases, processing this object might just include forwarding it to the next filter by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556314">IXpsDocumentConsumer::SendXpsUnknown</a> method.

Filters can also create discard controls. To create a discard control, the filter must create an object that implements the <b>IPartDiscardControl</b> interface. Because the filter transfers ownership of the discard control when it sends it to the next filter, the filter must manage the lifetime of the discard control. If a filter creates a discard control, the filter DLL must not unload until the discard control has been released.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartDiscardControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPartDiscardControl</b> also has these types of members:

The <b>IPartDiscardControl</b> interface has these methods.

The <b>GetDiscardProperties</b> method gets the properties of the discard control.

 


## -members
The <b>IPartDiscardControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551885">IPartDiscardControl::GetDiscardProperties</a>
</td>
<td align="left" width="63%">
The <b>GetDiscardProperties</b> method gets the properties of the discard control.

</td>
</tr>
</table>The <b>GetDiscardProperties</b> method gets the properties of the discard control.

 


## -remarks
