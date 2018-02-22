---
UID: NF:dbgeng.IDebugSymbols3.SetSourcePath
title: IDebugSymbols3::SetSourcePath method
author: windows-driver-content
description: The SetSourcePath method sets the source path.
old-location: debugger\setsourcepath.htm
old-project: Debugger
ms.assetid: 00b5927e-4b95-4528-bc09-da90db8a7716
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.setsourcepath, IDebugSymbols_d592ec7c-56f9-46b2-9627-d79e8fdba5c4.xml, dbgeng/IDebugSymbols3::SetSourcePath, IDebugSymbols3::SetSourcePath, SetSourcePath, IDebugSymbols2 interface [Windows Debugging], SetSourcePath method, SetSourcePath method [Windows Debugging], IDebugSymbols2 interface, dbgeng/IDebugSymbols2::SetSourcePath, SetSourcePath method [Windows Debugging], SetSourcePath method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols, IDebugSymbols3, SetSourcePath method [Windows Debugging], IDebugSymbols interface, IDebugSymbols3 interface [Windows Debugging], SetSourcePath method, dbgeng/IDebugSymbols::SetSourcePath, IDebugSymbols2::SetSourcePath, IDebugSymbols2, IDebugSymbols interface [Windows Debugging], SetSourcePath method, IDebugSymbols::SetSourcePath
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols.SetSourcePath
-	IDebugSymbols2.SetSourcePath
-	IDebugSymbols3.SetSourcePath
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::SetSourcePath method


## -description


The <b>SetSourcePath</b>  method sets the source path.


## -syntax


````
HRESULT SetSourcePath(
  [in] PCSTR Path
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::SetSourcePath method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

