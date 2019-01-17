---
UID: NF:dbgeng.IDebugSymbols3.SetSourcePathWide
title: IDebugSymbols3::SetSourcePathWide
description: The SetSourcePathWide method sets the source path.
old-location: debugger\setsourcepathwide.htm
tech.root: debugger
ms.assetid: 1fdb4e2c-ece7-407e-840c-fbd6dfe46d78
ms.date: 05/03/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetSourcePathWide method, IDebugSymbols3.SetSourcePathWide, IDebugSymbols3::SetSourcePathWide, SetSourcePathWide, SetSourcePathWide method [Windows Debugging], SetSourcePathWide method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetSourcePathWide, debugger.setsourcepathwide
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
-	IDebugSymbols3.SetSourcePathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::SetSourcePathWide


## -description


The <b>SetSourcePathWide</b>  method sets the source path.


## -parameters




### -param Path [in]

Specifies the new source path.  This is a string that contains source path elements separated by semicolons (<b>;</b>).  Each source path element can specify either a directory or a source server.


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
</table>
 




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538102">AppendSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

