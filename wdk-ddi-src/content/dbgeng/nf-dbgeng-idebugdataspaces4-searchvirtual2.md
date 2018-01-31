---
UID: NF:dbgeng.IDebugDataSpaces4.SearchVirtual2
title: IDebugDataSpaces4::SearchVirtual2 method
author: windows-driver-content
description: The SearchVirtual2 method searches the process's virtual memory for a specified pattern of bytes.
old-location: debugger\searchvirtual2.htm
old-project: debugger
ms.assetid: f54c35da-d455-4700-b8b9-c4479bc95088
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugDataSpaces4::SearchVirtual2, IDebugDataSpaces_62e68b69-35f7-4d69-bcf2-93b74fe0aa72.xml, SearchVirtual2 method [Windows Debugging], IDebugDataSpaces4 interface, SearchVirtual2, IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], SearchVirtual2 method, SearchVirtual2 method [Windows Debugging], debugger.searchvirtual2, IDebugDataSpaces4::SearchVirtual2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
-	IDebugDataSpaces4.SearchVirtual2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::SearchVirtual2 method


## -description


The <b>SearchVirtual2</b> method searches the process's virtual memory for a specified pattern of bytes.


## -syntax


````
HRESULT SearchVirtual2(
  [in]  ULONG64  Offset,
  [in]  ULONG64  Length,
  [in]  ULONG    Flags,
  [in]  PVOID    Pattern,
  [in]  ULONG    PatternSize,
  [in]  ULONG    PatternGranularity,
  [out] PULONG64 MatchOffset
);
````


## -parameters




#### - Offset [in]

Specifies the location in the process's virtual address space to start searching for the pattern.


#### - Length [in]

Specifies how far to search for the pattern.  A successful match requires the entire pattern to be found before <i>Length</i> bytes have been examined.


#### - Flags [in]

Specifies a bit field of flags for the search.  Currently, the only bit-flag that can be set is DEBUG_VSEARCH_WRITABLE_ONLY, which restricts the search to writable memory.


#### - Pattern [in]

Specifies the pattern to search for.


#### - PatternSize [in]

Specifies the size, in bytes, of the pattern.  This must be a multiple of the granularity of the pattern.


#### - PatternGranularity [in]

Specifies the granularity of the pattern.  For a successful match, the difference between the location of the found pattern and <i>Offset</i> must be a multiple of <i>PatternGranularity</i>.


#### - MatchOffset [out]

Receives the location in the process's virtual address space of the pattern, if it was found.


## -returns


This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_MORE_ENTRIES)</b></dt>
</dl>
</td>
<td width="60%">
After examining <i>Length</i> bytes, the pattern was not found.

</td>
</tr>
</table> 



## -remarks


This method searches the target's virtual memory for the first occurrence, subject to granularity, of the pattern that is entirely contained in the <i>Length</i> bytes of the target's memory, starting at the <i>Offset</i> location.

<i>PatternGranularity</i> can be used to ensure the alignment of the match relative to <i>Offset</i>.  For example, a value of 0x4 can be used to require alignment to a DWORD.  A value of 0x1 can be used to allow the pattern to start anywhere.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554747">SearchVirtual</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces4::SearchVirtual2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

