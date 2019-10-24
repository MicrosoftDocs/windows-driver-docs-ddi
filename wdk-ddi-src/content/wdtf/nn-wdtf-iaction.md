---
UID: NN:wdtf.IAction
title: IAction (wdtf.h)
description: The IAction interfaces are plug-ins that can control an instance of the IWDTFTarget2 interface.
old-location: dtf\iaction.htm
tech.root: dtf
ms.assetid: 9bc709cb-1adb-4b70-b8cb-9168ccb7b259
ms.date: 04/04/2018
ms.keywords: IAction, IAction interface [Windows Device Testing Framework], IAction interface [Windows Device Testing Framework],described, IAction_d82d1b27-acd4-43f6-b020-a9a9fa5dbe60.xml, Microsoft.WDTF.IAction, dtf.iaction, wdtf/IAction
ms.topic: interface
f1_keywords:
 - "wdtf/IAction"
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
- WDTF.Interop.metadata_dll.dll
api_name:
- IAction
- IAction.SetTarget
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAction interface


## -description


The <b>IAction</b> interfaces are plug-ins that can control an instance of the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAction</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a>. <b>IAction</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IAction</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetTarget</b></td>
<td align="left" width="63%">
You should not directly call this method. <b>SetTarget</b> is used internally by 
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a> method to find the correct implementation as well as provide the targets for the implementation to use in whatever actions it performs.

</td>
</tr>
</table> 


## -remarks



You can retrieve an <b>IAction</b> interface for a target by calling 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a>.

The <b>IAction</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a>. You can use <b>ITracing</b> to set the trace level of the action.

Domain experts use this interface as a base for implementing a WDTF plug-in (that is, action) that can 
control an instance of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface. For more information about action interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdtf/controlling-targets">Controlling Targets</a>.

For a listing of all action interfaces included in WDTF, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Action Interfaces</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ITracing</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a>
 

 

