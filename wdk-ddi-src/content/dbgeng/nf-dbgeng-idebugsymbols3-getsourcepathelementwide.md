---
UID: NF:dbgeng.IDebugSymbols3.GetSourcePathElementWide
title: IDebugSymbols3::GetSourcePathElementWide method
author: windows-driver-content
description: The GetSourcePathElementWide method returns an element from the source path.
old-location: debugger\getsourcepathelementwide.htm
old-project: debugger
ms.assetid: 724ee7a6-a0ef-440b-a0d4-5eecda77338a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSourcePathElementWide method [Windows Debugging], IDebugSymbols3::GetSourcePathElementWide, dbgeng/IDebugSymbols3::GetSourcePathElementWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourcePathElementWide method, GetSourcePathElementWide, GetSourcePathElementWide method [Windows Debugging], IDebugSymbols3 interface, debugger.getsourcepathelementwide
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
-	IDebugSymbols3.GetSourcePathElementWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourcePathElementWide method


## -description


The <b>GetSourcePathElementWide</b>  method returns an element from the source path.


## -syntax


````
HRESULT GetSourcePathElementWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG ElementSize
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourcePathElementWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

