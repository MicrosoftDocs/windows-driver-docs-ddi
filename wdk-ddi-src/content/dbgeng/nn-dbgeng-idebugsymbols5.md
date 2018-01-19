---
UID: NN:dbgeng.IDebugSymbols5
title: IDebugSymbols5
author: windows-driver-content
description: This interface supports using index values for the current frame.
old-location: debugger\idebugsymbols5.htm
old-project: debugger
ms.assetid: 0D239C0E-96C8-49F9-BDFD-182F3F7C3976
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols5
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols5 interface



## -description
This interface supports using index values for the current frame. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbols5</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugSymbols5</b> also has these types of members:

The <b>IDebugSymbols5</b> interface has these methods.

Gets the index of the current frame.

Sets the current frame by using an index.

 


## -members
The <b>IDebugSymbols5</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0D8198BB-583F-4828-8131-61EB17621F32">GetCurrentScopeFrameIndexEx</a>
</td>
<td align="left" width="63%">
Gets the index of the current frame.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/E0638C55-4160-48A5-9378-6AA9AAC8DC36">SetScopeFrameByIndexEx</a>
</td>
<td align="left" width="63%">
Sets the current frame by using an index.

</td>
</tr>
</table>Gets the index of the current frame.

Sets the current frame by using an index.

 


## -remarks
