---
UID: NN:wdtf.IWDTFAction2
title: IWDTFAction2
author: windows-driver-content
description: Defines operations and properties that can control an instance of the IWDTFTarget2 interface.
old-location: dtf\iwdtfaction2.htm
old-project: dtf
ms.assetid: 0ca56301-9e46-4082-a5a4-41a9c655fbd8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], IWDTFAction2 interface [Windows Device Testing Framework], described, Microsoft.WDTF.IWDTFAction2, dtf.iwdtfaction2, wdtf/IWDTFAction2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFAction2
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFAction2 interface


## -description


Defines operations and properties that can control an instance of the 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFAction2</b> interface inherits from <b>IAction</b>. <b>IWDTFAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406383">DisableObjectErrorLogging</a>
</td>
<td align="left" width="63%">
Disables object error logging for the action.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406315">DisableObjectLogging</a>
</td>
<td align="left" width="63%">
Disables object logging for the action.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406317">EnableObjectErrorLogging</a>
</td>
<td align="left" width="63%">
Enables object error logging for the action.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406319">EnableObjectLogging</a>
</td>
<td align="left" width="63%">
Enables object logging for the action.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406321">GetStatus</a>
</td>
<td align="left" width="63%">
Returns the status code for the last operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406323">GetStatusString</a>
</td>
<td align="left" width="63%">
Returns the status for the last operation as a string.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406325">IsStatusSuccess</a>
</td>
<td align="left" width="63%">
Gets a value that indicates whether the last operation was successful.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFAction2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406329">Target</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the target to which this action refers.

</td>
</tr>
</table> 

