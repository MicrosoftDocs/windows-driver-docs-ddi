---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolTypeNameWide
title: IDebugSymbolGroup2::GetSymbolTypeNameWide
author: windows-driver-content
description: The GetSymbolTypeNameWide method returns the name of the specified symbol's type.
old-location: debugger\getsymboltypenamewide.htm
old-project: debugger
ms.assetid: 1e5b71cf-98c4-42bc-984d-6278ff30e8c1
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetSymbolTypeNameWide, GetSymbolTypeNameWide method [Windows Debugging], GetSymbolTypeNameWide method [Windows Debugging],IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging],GetSymbolTypeNameWide method, IDebugSymbolGroup2.GetSymbolTypeNameWide, IDebugSymbolGroup2::GetSymbolTypeNameWide, dbgeng/IDebugSymbolGroup2::GetSymbolTypeNameWide, debugger.getsymboltypenamewide
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
-	IDebugSymbolGroup2.GetSymbolTypeNameWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbolGroup2::GetSymbolTypeNameWide


## -description


The <b>GetSymbolTypeNameWide</b> method returns the name of the specified symbol's type.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/09aa3ba9-d5b6-4c08-93f1-f7beca9350a1">IDebugSymbols::GetTypeName</a>
 

 

