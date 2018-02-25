---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolNameWide
title: IDebugSymbolGroup2::GetSymbolNameWide method
author: windows-driver-content
description: The GetSymbolNameWide method returns the name of a symbol in a symbol group.
old-location: debugger\getsymbolnamewide.htm
old-project: debugger
ms.assetid: b5de2450-8003-4866-86e8-1fd251e1552c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 2, :, D, G, GetSymbolNameWide method [Windows Debugging], GetSymbolNameWide method [Windows Debugging], IDebugSymbolGroup2 interface, GetSymbolNameWide,IDebugSymbolGroup2.GetSymbolNameWide, I, IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolNameWide method, IDebugSymbolGroup2::GetSymbolNameWide, N, S, W, a, b, d, dbgeng/IDebugSymbolGroup2::GetSymbolNameWide, debugger.getsymbolnamewide, e, g, i, l, m, o, p, r, t, u, y"
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
-	IDebugSymbolGroup2.GetSymbolNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::GetSymbolNameWide method


## -description


The <b>GetSymbolNameWide</b> method returns the name of a symbol in a symbol group.


## -syntax


````
HRESULT GetSymbolNameWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG NameSize
);
````


## -parameters




### -param Index [in]

The index of the symbol whose name you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Buffer [out, optional]

The symbol name.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size of the buffer that <i>Buffer </i>points to.


### -param NameSize [out, optional]

The size of the symbol name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the name of the symbol did not fit in the buffer referred to by the <i>Buffer</i> parameter, so a truncated name was returned.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolNameWide method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

