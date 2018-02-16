---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolValueTextWide
title: IDebugSymbolGroup2::GetSymbolValueTextWide method
author: windows-driver-content
description: The GetSymbolValueTextWide method returns a string that represents the value of a symbol.
old-location: debugger\getsymbolvaluetextwide.htm
old-project: debugger
ms.assetid: 56e147ea-497b-4691-8a62-8165828b1f36
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSymbolValueTextWide method [Windows Debugging], IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolValueTextWide method, GetSymbolValueTextWide method [Windows Debugging], IDebugSymbolGroup2 interface, debugger.getsymbolvaluetextwide, GetSymbolValueTextWide, IDebugSymbolGroup2::GetSymbolValueTextWide, dbgeng/IDebugSymbolGroup2::GetSymbolValueTextWide, IDebugSymbolGroup2
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
-	IDebugSymbolGroup2.GetSymbolValueTextWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbolGroup2::GetSymbolValueTextWide method


## -description


The <b>GetSymbolValueTextWide</b> method returns a string that represents the value of a symbol.


## -syntax


````
HRESULT GetSymbolValueTextWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG NameSize
);
````


## -parameters




### -param Index [in]

The index of the symbol whose value you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Buffer [out, optional]

The value of the symbol as a string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size, in characters, of the <i>Buffer </i>buffer.


### -param NameSize [out, optional]

The size, in characters, of the value of the symbol.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful.  However, the value of the symbol would not fit in the buffer referred to by the <i>Buffer</i> parameter, so a truncated value was returned.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



If you added the symbol to the symbol group by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a> method, the string that is returned to <i>Buffer</i> is the name of the symbol that is passed to <b>AddSymbol</b>.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561457">WriteSymbol</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolValueTextWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

