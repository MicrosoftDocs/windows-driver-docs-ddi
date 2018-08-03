---
UID: NF:dbgeng.IDebugControl4.GetSpecificFilterArgumentWide
title: IDebugControl4::GetSpecificFilterArgumentWide
author: windows-driver-content
description: The GetSpecificFilterArgumentWide method returns the value of filter argument for thespecific filters that have an argument.
old-location: debugger\getspecificfilterargumentwide.htm
tech.root: debugger
ms.assetid: 61537680-0453-4484-b07a-e0d90b45c412
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetSpecificFilterArgumentWide, GetSpecificFilterArgumentWide method [Windows Debugging], GetSpecificFilterArgumentWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetSpecificFilterArgumentWide method, IDebugControl4.GetSpecificFilterArgumentWide, IDebugControl4::GetSpecificFilterArgumentWide, dbgeng/IDebugControl4::GetSpecificFilterArgumentWide, debugger.getspecificfilterargumentwide
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
-	IDebugControl4.GetSpecificFilterArgumentWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetSpecificFilterArgumentWide


## -description


The <b>GetSpecificFilterArgumentWide</b>  method returns the value of filter argument for thespecific filters that have an argument.


## -parameters




### -param Index [in]

Specifies the index of the specific filter whose argument will be returned.  <i>Index</i> must be the index of a specific filter that has an argument.


### -param Buffer [out, optional]

Receives the argument for the specific filter.  The interpretation of the argument depends on the specific filter.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param ArgumentSize [out, optional]

Receives the size, in characters, of the argument for the specific filter.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For a list of specific filters that have argument and the interpretation of those arguments, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556791">SetSpecificFilterArgument</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

