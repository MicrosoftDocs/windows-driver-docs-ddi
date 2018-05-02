---
UID: NF:dbgeng.IDebugSymbols.AppendSourcePath
title: IDebugSymbols::AppendSourcePath
author: windows-driver-content
description: The AppendSourcePath method appends directories to the source path.
old-location: debugger\appendsourcepath.htm
old-project: debugger
ms.assetid: b82c2206-b81d-4ebf-a8fd-c08d7f57ffc9
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: AppendSourcePath, AppendSourcePath method [Windows Debugging], AppendSourcePath method [Windows Debugging],IDebugSymbols interface, AppendSourcePath method [Windows Debugging],IDebugSymbols2 interface, AppendSourcePath method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],AppendSourcePath method, IDebugSymbols.AppendSourcePath, IDebugSymbols2 interface [Windows Debugging],AppendSourcePath method, IDebugSymbols2::AppendSourcePath, IDebugSymbols3 interface [Windows Debugging],AppendSourcePath method, IDebugSymbols3::AppendSourcePath, IDebugSymbols::AppendSourcePath, IDebugSymbols_8e47c1ea-e190-4f34-a952-1dcf4ef9e971.xml, dbgeng/IDebugSymbols2::AppendSourcePath, dbgeng/IDebugSymbols3::AppendSourcePath, dbgeng/IDebugSymbols::AppendSourcePath, debugger.appendsourcepath
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
-	Dbgeng.h
api_name:
-	IDebugSymbols.AppendSourcePath
-	IDebugSymbols2.AppendSourcePath
-	IDebugSymbols3.AppendSourcePath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::AppendSourcePath


## -description


The <b>AppendSourcePath</b>  method appends directories to the source path.


## -parameters




### -param Addition [in]

Specifies the directories to append to the source path.  This is a string that contains source path elements separated by semicolons (;).  Each source path element can specify either a directory or a source server.


## -returns



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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556781">SetSourcePath</a>
 

 

