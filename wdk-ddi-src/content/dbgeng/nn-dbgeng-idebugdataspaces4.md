---
UID: NN:dbgeng.IDebugDataSpaces4
title: IDebugDataSpaces4
author: windows-driver-content
description: IDebugDataSpaces4 interface
old-location: debugger\idebugdataspaces4.htm
old-project: debugger
ms.assetid: e03202a5-2e4a-43f8-8183-fdd26df6ff8f
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], IDebugDataSpaces4 interface [Windows Debugging],described, dbgeng/IDebugDataSpaces4, debugger.idebugdataspaces4
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
-	dbgeng.h
api_name:
-	IDebugDataSpaces4
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces4 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugDataSpaces4</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550537">IDebugDataSpaces3</a>. <b>IDebugDataSpaces4</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugDataSpaces4</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547847">GetNextDifferentlyValidOffsetVirtual</a>
</td>
<td align="left" width="63%">
Returns the offset of the next address whose validity might be different from the validity of the specified address.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548055">GetOffsetInformation</a>
</td>
<td align="left" width="63%">
Provides general information about an address in a process's data space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549471">GetValidRegionVirtual</a>
</td>
<td align="left" width="63%">
Locates the first valid region of memory in a specified memory range.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554300">ReadMultiByteStringVirtual</a>
</td>
<td align="left" width="63%">
Reads a null-terminated, multibyte string from the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554304">ReadMultiByteStringVirtualWide</a>
</td>
<td align="left" width="63%">
Reads a null-terminated, multibyte string from the target and converts it to Unicode.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554311">ReadPhysical2</a>
</td>
<td align="left" width="63%">
Reads the target's memory from the specified physical address.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554351">ReadUnicodeStringVirtual</a>
</td>
<td align="left" width="63%">
Reads a null-terminated, Unicode string from the target and converts it to a multibyte string.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554357">ReadUnicodeStringVirtualWide</a>
</td>
<td align="left" width="63%">
Reads a null-terminated, Unicode string from the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554755">SearchVirtual2</a>
</td>
<td align="left" width="63%">
Searches the process's virtual memory for a specified pattern of bytes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561441">WritePhysical2</a>
</td>
<td align="left" width="63%">
Writes data to the specified physical address in the target's memory.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550528">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550531">IDebugDataSpaces2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550537">IDebugDataSpaces3</a>
 

 

