---
UID: NF:dbgeng.IDebugSymbols2.SetSourcePath
title: IDebugSymbols2::SetSourcePath
author: windows-driver-content
description: The SetSourcePath method sets the source path.
old-location: debugger\setsourcepath.htm
old-project: debugger
ms.assetid: 00b5927e-4b95-4528-bc09-da90db8a7716
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugSymbols interface [Windows Debugging],SetSourcePath method, IDebugSymbols2 interface [Windows Debugging],SetSourcePath method, IDebugSymbols2.SetSourcePath, IDebugSymbols2::SetSourcePath, IDebugSymbols3 interface [Windows Debugging],SetSourcePath method, IDebugSymbols3::SetSourcePath, IDebugSymbols::SetSourcePath, IDebugSymbols_d592ec7c-56f9-46b2-9627-d79e8fdba5c4.xml, SetSourcePath, SetSourcePath method [Windows Debugging], SetSourcePath method [Windows Debugging],IDebugSymbols interface, SetSourcePath method [Windows Debugging],IDebugSymbols2 interface, SetSourcePath method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols2::SetSourcePath, dbgeng/IDebugSymbols3::SetSourcePath, dbgeng/IDebugSymbols::SetSourcePath, debugger.setsourcepath
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
-	IDebugSymbols.SetSourcePath
-	IDebugSymbols2.SetSourcePath
-	IDebugSymbols3.SetSourcePath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::SetSourcePath


## -description


The <b>SetSourcePath</b>  method sets the source path.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

