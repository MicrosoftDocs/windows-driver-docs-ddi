---
UID: NN:dbgeng.IDebugDataSpaces4
title: IDebugDataSpaces4
author: windows-driver-content
description: IDebugDataSpaces4 interface
old-location: debugger\idebugdataspaces4.htm
old-project: debugger
ms.assetid: e03202a5-2e4a-43f8-8183-fdd26df6ff8f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugdataspaces4, IDebugDataSpaces4 interface [Windows Debugging], IDebugDataSpaces4 interface [Windows Debugging], described, IDebugDataSpaces4, dbgeng/IDebugDataSpaces4
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugDataSpaces4
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4 interface


## -description




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
</table>Returns the offset of the next address whose validity might be different from the validity of the specified address.

Provides general information about an address in a process's data space.

Locates the first valid region of memory in a specified memory range.

Reads a null-terminated, multibyte string from the target.

Reads a null-terminated, multibyte string from the target and converts it to Unicode.

Reads the target's memory from the specified physical address.

Reads a null-terminated, Unicode string from the target and converts it to a multibyte string.

Reads a null-terminated, Unicode string from the target.

Searches the process's virtual memory for a specified pattern of bytes.

Writes data to the specified physical address in the target's memory.

 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces4 interface%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

