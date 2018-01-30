---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolTypeNameWide
title: IDebugSymbolGroup2::GetSymbolTypeNameWide method
author: windows-driver-content
description: The GetSymbolTypeNameWide method returns the name of the specified symbol's type.
old-location: debugger\getsymboltypenamewide.htm
old-project: debugger
ms.assetid: 1e5b71cf-98c4-42bc-984d-6278ff30e8c1
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbolGroup2::GetSymbolTypeNameWide, GetSymbolTypeNameWide method [Windows Debugging], dbgeng/IDebugSymbolGroup2::GetSymbolTypeNameWide, debugger.getsymboltypenamewide, IDebugSymbolGroup2, GetSymbolTypeNameWide method [Windows Debugging], IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolTypeNameWide method, GetSymbolTypeNameWide
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
-	IDebugSymbolGroup2.GetSymbolTypeNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::GetSymbolTypeNameWide method


## -description


The <b>GetSymbolTypeNameWide</b> method returns the name of the specified symbol's type.


## -syntax


````
HRESULT GetSymbolTypeNameWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG NameSize
);
````


## -parameters




### -param Index [in]

The index of the symbol whose type name you want. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Buffer [out, optional]

The name of the symbol's type.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size, in characters, of the <i>Buffer</i> buffer.


### -param NameSize [out, optional]

The size, in characters, of the name of the symbol's type.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer was smaller than the size of the name of the symbol's type. The buffer is filled with the truncated name.

</td>
</tr>
</table> 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.



## -remarks


For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.



## -see-also

<a href="https://msdn.microsoft.com/09aa3ba9-d5b6-4c08-93f1-f7beca9350a1">IDebugSymbols::GetTypeName</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolTypeNameWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

