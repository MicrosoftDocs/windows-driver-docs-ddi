---
UID: NF:dbgeng.IDebugSymbols2.AppendSourcePath
title: IDebugSymbols2::AppendSourcePath method
author: windows-driver-content
description: The AppendSourcePath method appends directories to the source path.
old-location: debugger\appendsourcepath.htm
old-project: debugger
ms.assetid: b82c2206-b81d-4ebf-a8fd-c08d7f57ffc9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AppendSourcePath method [Windows Debugging], AppendSourcePath method [Windows Debugging], IDebugSymbols interface, AppendSourcePath method [Windows Debugging], IDebugSymbols2 interface, AppendSourcePath method [Windows Debugging], IDebugSymbols3 interface, AppendSourcePath,IDebugSymbols2.AppendSourcePath, IDebugSymbols interface [Windows Debugging], AppendSourcePath method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], AppendSourcePath method, IDebugSymbols2::AppendSourcePath, IDebugSymbols3 interface [Windows Debugging], AppendSourcePath method, IDebugSymbols3::AppendSourcePath, IDebugSymbols::AppendSourcePath, IDebugSymbols_8e47c1ea-e190-4f34-a952-1dcf4ef9e971.xml, dbgeng/IDebugSymbols2::AppendSourcePath, dbgeng/IDebugSymbols3::AppendSourcePath, dbgeng/IDebugSymbols::AppendSourcePath, debugger.appendsourcepath
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
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::AppendSourcePath method


## -description


The <b>AppendSourcePath</b>  method appends directories to the source path.


## -syntax


````
HRESULT AppendSourcePath(
  [in] PCSTR Addition
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556781">SetSourcePath</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::AppendSourcePath method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

