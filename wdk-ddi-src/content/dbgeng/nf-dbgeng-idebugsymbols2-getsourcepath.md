---
UID: NF:dbgeng.IDebugSymbols2.GetSourcePath
title: IDebugSymbols2::GetSourcePath method
author: windows-driver-content
description: The GetSourcePath method returns the source path.
old-location: debugger\getsourcepath.htm
old-project: debugger
ms.assetid: 93a1efce-5f93-4a09-aa61-ffbd3d619176
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetSourcePath method [Windows Debugging], GetSourcePath method [Windows Debugging], IDebugSymbols interface, GetSourcePath method [Windows Debugging], IDebugSymbols2 interface, GetSourcePath method [Windows Debugging], IDebugSymbols3 interface, GetSourcePath,IDebugSymbols2.GetSourcePath, IDebugSymbols interface [Windows Debugging], GetSourcePath method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], GetSourcePath method, IDebugSymbols2::GetSourcePath, IDebugSymbols3 interface [Windows Debugging], GetSourcePath method, IDebugSymbols3::GetSourcePath, IDebugSymbols::GetSourcePath, IDebugSymbols_cbdf5e16-41ba-4134-b41b-81164dfc07a0.xml, dbgeng/IDebugSymbols2::GetSourcePath, dbgeng/IDebugSymbols3::GetSourcePath, dbgeng/IDebugSymbols::GetSourcePath, debugger.getsourcepath
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
-	IDebugSymbols.GetSourcePath
-	IDebugSymbols2.GetSourcePath
-	IDebugSymbols3.GetSourcePath
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::GetSourcePath method


## -description


The <b>GetSourcePath</b>  method returns the source path.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556781">SetSourcePath</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetSourcePath method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

