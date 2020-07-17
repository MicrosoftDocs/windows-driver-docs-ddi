---
UID: NF:dbgeng.IDebugControl4.SetSpecificFilterArgumentWide
title: IDebugControl4::SetSpecificFilterArgumentWide (dbgeng.h)
description: The SetSpecificFilterArgumentWide method sets the value of filter argument for the specific filters that can have an argument.
old-location: debugger\setspecificfilterargumentwide.htm
tech.root: debugger
ms.assetid: 416c4de2-f200-491a-a319-fb0a4fd86f86
ms.date: 05/03/2018
keywords: ["IDebugControl4::SetSpecificFilterArgumentWide"]
ms.keywords: IDebugControl4 interface [Windows Debugging],SetSpecificFilterArgumentWide method, IDebugControl4.SetSpecificFilterArgumentWide, IDebugControl4::SetSpecificFilterArgumentWide, SetSpecificFilterArgumentWide, SetSpecificFilterArgumentWide method [Windows Debugging], SetSpecificFilterArgumentWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetSpecificFilterArgumentWide, debugger.setspecificfilterargumentwide
f1_keywords:
 - "dbgeng/IDebugControl4.SetSpecificFilterArgumentWide"
 - "IDebugControl4.SetSpecificFilterArgumentWide"
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
- IDebugControl4.SetSpecificFilterArgumentWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::SetSpecificFilterArgumentWide


## -description


The <b>SetSpecificFilterArgumentWide</b>  method sets the value of filter argument for the specific filters that can have an argument.


## -parameters




### -param Index [in]

Specifies the index of the specific filter whose argument will be set.  <i>Index</i> must be the index of a specific filter that has an argument.


### -param Argument [in]

Specifies the argument for the specific filter.  The interpretation of this argument depends on the specific filter.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> does not refer to a specific filter that has an argument.

</td>
</tr>
</table>
 




## -remarks



For a list of specific filters that have argument and the interpretation of those arguments, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getspecificfilterargument">GetSpecificFilterArgument</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

