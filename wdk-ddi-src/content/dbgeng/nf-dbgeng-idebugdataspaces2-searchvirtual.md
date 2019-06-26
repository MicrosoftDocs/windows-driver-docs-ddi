---
UID: NF:dbgeng.IDebugDataSpaces2.SearchVirtual
title: IDebugDataSpaces2::SearchVirtual (dbgeng.h)
description: The SearchVirtual method searches the target's virtual memory for a specified pattern of bytes.
old-location: debugger\searchvirtual.htm
tech.root: debugger
ms.assetid: 1cb779de-fcbb-450d-9932-0cdaa9fbb1e9
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging],SearchVirtual method, IDebugDataSpaces2 interface [Windows Debugging],SearchVirtual method, IDebugDataSpaces2.SearchVirtual, IDebugDataSpaces2::SearchVirtual, IDebugDataSpaces3 interface [Windows Debugging],SearchVirtual method, IDebugDataSpaces3::SearchVirtual, IDebugDataSpaces4 interface [Windows Debugging],SearchVirtual method, IDebugDataSpaces4::SearchVirtual, IDebugDataSpaces::SearchVirtual, IDebugDataSpaces_9af5d620-f8df-430c-88ab-0d4f96844499.xml, SearchVirtual, SearchVirtual method [Windows Debugging], SearchVirtual method [Windows Debugging],IDebugDataSpaces interface, SearchVirtual method [Windows Debugging],IDebugDataSpaces2 interface, SearchVirtual method [Windows Debugging],IDebugDataSpaces3 interface, SearchVirtual method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::SearchVirtual, dbgeng/IDebugDataSpaces3::SearchVirtual, dbgeng/IDebugDataSpaces4::SearchVirtual, dbgeng/IDebugDataSpaces::SearchVirtual, debugger.searchvirtual
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugDataSpaces.SearchVirtual
- IDebugDataSpaces2.SearchVirtual
- IDebugDataSpaces3.SearchVirtual
- IDebugDataSpaces4.SearchVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2::SearchVirtual


## -description


The <b>SearchVirtual</b> method searches the target's virtual memory for a specified pattern of bytes.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space to start searching for the pattern.


### -param Length [in]

Specifies how far to search for the pattern.  A successful match requires the entire pattern to be found before <i>Length</i> bytes have been examined.


### -param Pattern [in]

Specifies the pattern to search for.


### -param PatternSize [in]

Specifies the size in bytes of the pattern.  This must be a multiple of the granularity of the pattern.


### -param PatternGranularity [in]

Specifies the granularity of the pattern.  For a successful match the pattern must occur a multiple of this value after the start location.


### -param MatchOffset [out]

Receives the location in the target's virtual address space of the pattern, if it was found.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
After examining <i>Length</i> bytes the pattern was not found.

</td>
</tr>
</table>
 




## -remarks



This method searches the target's virtual memory for the first occurrence, subject to granularity, of the pattern entirely contained in the <i>Length</i> bytes of the target's memory starting at the location <i>Offset</i>.

<i>PatternGranularity</i> can be used to ensure the alignment of the match relative to <i>Offset</i>.  For example, a value of 0x4 can be used to require alignment to a DWORD.  A value of 0x1 can be used to allow the pattern to start anywhere.

For additional options, including the ability to restrict the search to writable memory, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-searchvirtual2">SearchVirtual2</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtual">ReadVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-searchvirtual2">SearchVirtual2</a>
 

 

