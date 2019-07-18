---
UID: NN:wdtf.IWDTFActions2
title: IWDTFActions2 (wdtf.h)
description: Defines operations and properties for the collection of actions that the IWDTFTargets::GetInterfaces method returns.
old-location: dtf\iwdtfactions2.htm
tech.root: dtf
ms.assetid: cf78bd7f-7d92-421f-8f68-e56db5e7c7d4
ms.date: 04/04/2018
ms.keywords: IWDTFActions2, IWDTFActions2 interface [Windows Device Testing Framework], IWDTFActions2 interface [Windows Device Testing Framework],described, dtf.iwdtfactions2, wdtf/IWDTFActions2
ms.topic: interface
f1_keywords:
 - "wdtf/IWDTFActions2"
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Wdtf.idl
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
- wdtf.h
api_name:
- IWDTFActions2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFActions2 interface


## -description


Defines operations and properties for the collection of actions that the IWDTFTargets::GetInterfaces 
method returns.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFActions2</b> interface inherits from <b>ITracing</b>. <b>IWDTFActions2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFActions2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/test/wpt/add">Add</a>
</td>
<td align="left" width="63%">
Add a single action to the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Clear</a>
</td>
<td align="left" width="63%">
Removes all items from the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfconfig2-disableobjecterrorlogging">DisableObjectErrorLogging</a>
</td>
<td align="left" width="63%">
Disable object error logging for all actions in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfaction2-disableobjectlogging">DisableObjectLogging</a>
</td>
<td align="left" width="63%">
Disable object logging for all actions in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfaction2-enableobjecterrorlogging">EnableObjectErrorLogging</a>
</td>
<td align="left" width="63%">
Enable object error logging for all actions in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfaction2-enableobjectlogging">EnableObjectLogging</a>
</td>
<td align="left" width="63%">
Enable object logging for all actions in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftargets2-remove">Remove</a>
</td>
<td align="left" width="63%">
Remove an action from the collection.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFActions2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfstrings2-get__newenum">_NewEnum</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a new iteration variable that the <b>For Each</b> 
loop structure implicitly uses.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406342(v=vs.85)">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the number of actions in this collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfnumbers2-get_item">Item</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets an individual action in the collection.

</td>
</tr>
</table> 

