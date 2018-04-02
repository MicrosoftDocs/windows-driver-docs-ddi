---
UID: NF:dbgeng.IDebugSymbols3.GetSourcePathWide
title: IDebugSymbols3::GetSourcePathWide method
author: windows-driver-content
description: The GetSourcePathWide method returns the source path.
old-location: debugger\getsourcepathwide.htm
old-project: debugger
ms.assetid: 6c9c8270-78c4-4bc2-a0e4-5c5e245326ad
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSourcePathWide method [Windows Debugging], GetSourcePathWide method [Windows Debugging], IDebugSymbols3 interface, GetSourcePathWide,IDebugSymbols3.GetSourcePathWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourcePathWide method, IDebugSymbols3::GetSourcePathWide, dbgeng/IDebugSymbols3::GetSourcePathWide, debugger.getsourcepathwide
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
-	IDebugSymbols3.GetSourcePathWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourcePathWide method


## -description


The <b>GetSourcePathWide</b>  method returns the source path.


## -parameters




### -param Buffer [out, optional]

Receives the source path.  This is a string that contains source path elements separated by semicolons (<b>;</b>).  Each source path element can specify either a directory or a source server.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param PathSize [out, optional]

Receives the size, in characters, of the source path.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the source path and the path was truncated.

</td>
</tr>
</table>
 




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538102">AppendSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556781">SetSourcePath</a>
 

 

