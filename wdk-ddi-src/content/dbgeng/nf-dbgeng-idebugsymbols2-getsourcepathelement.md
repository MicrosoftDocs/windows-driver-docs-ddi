---
UID: NF:dbgeng.IDebugSymbols2.GetSourcePathElement
title: IDebugSymbols2::GetSourcePathElement
author: windows-driver-content
description: The GetSourcePathElement method returns an element from the source path.
old-location: debugger\getsourcepathelement.htm
tech.root: debugger
ms.assetid: 69507aed-ff32-46f2-8efb-68c1a7288bfb
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetSourcePathElement, GetSourcePathElement method [Windows Debugging], GetSourcePathElement method [Windows Debugging],IDebugSymbols interface, GetSourcePathElement method [Windows Debugging],IDebugSymbols2 interface, GetSourcePathElement method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSourcePathElement method, IDebugSymbols2 interface [Windows Debugging],GetSourcePathElement method, IDebugSymbols2.GetSourcePathElement, IDebugSymbols2::GetSourcePathElement, IDebugSymbols3 interface [Windows Debugging],GetSourcePathElement method, IDebugSymbols3::GetSourcePathElement, IDebugSymbols::GetSourcePathElement, IDebugSymbols_517435f9-812c-43c2-bf82-5924de7955a2.xml, dbgeng/IDebugSymbols2::GetSourcePathElement, dbgeng/IDebugSymbols3::GetSourcePathElement, dbgeng/IDebugSymbols::GetSourcePathElement, debugger.getsourcepathelement
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
-	IDebugSymbols.GetSourcePathElement
-	IDebugSymbols2.GetSourcePathElement
-	IDebugSymbols3.GetSourcePathElement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetSourcePathElement


## -description


The <b>GetSourcePathElement</b>  method returns an element from the source path.


## -parameters




### -param Index [in]

Specifies the index of the element in the source path that will be returned.  The source path is a string that contains elements separated by semicolons (;).  The index of the first element is zero.


### -param Buffer [out, optional]

Receives the source path element.  Each source path element can be a directory or a source server.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param ElementSize [out, optional]

Receives the size, in characters, of the source path element.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The source path contains fewer than <i>Index</i> elements.

</td>
</tr>
</table>
 




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538102">AppendSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

