---
UID: NF:dbgeng.IDebugSymbols.GetNameByOffset
title: IDebugSymbols::GetNameByOffset method
author: windows-driver-content
description: The GetNameByOffset method returns the name of the symbol at the specified location in the target's virtual address space.
old-location: debugger\getnamebyoffset.htm
old-project: Debugger
ms.assetid: 47f87684-339a-49e0-a349-491054ab26ff
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.getnamebyoffset, dbgeng/IDebugSymbols3::GetNameByOffset, GetNameByOffset method [Windows Debugging], IDebugSymbols::GetNameByOffset, GetNameByOffset method [Windows Debugging], IDebugSymbols2 interface, GetNameByOffset method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols::GetNameByOffset, IDebugSymbols interface [Windows Debugging], GetNameByOffset method, GetNameByOffset, dbgeng/IDebugSymbols2::GetNameByOffset, IDebugSymbols_5045ed52-43b3-4f5c-90fe-d9725aeb5782.xml, IDebugSymbols3 interface [Windows Debugging], GetNameByOffset method, IDebugSymbols3::GetNameByOffset, GetNameByOffset method [Windows Debugging], IDebugSymbols interface, IDebugSymbols, IDebugSymbols2 interface [Windows Debugging], GetNameByOffset method, IDebugSymbols2::GetNameByOffset
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
-	IDebugSymbols.GetNameByOffset
-	IDebugSymbols2.GetNameByOffset
-	IDebugSymbols3.GetNameByOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::GetNameByOffset method


## -description


The <b>GetNameByOffset</b>  method returns the name of the symbol at the specified location in the target's virtual address space.


## -syntax


````
HRESULT GetNameByOffset(
  [in]            ULONG64  Offset,
  [out, optional] PSTR     NameBuffer,
  [in]            ULONG    NameBufferSize,
  [out, optional] PULONG   NameSize,
  [out, optional] PULONG64 Displacement
);
````


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the symbol whose name is requested.  <i>Offset</i> does not need to specify the base location of the symbol; it only needs to specify a location within the symbol's memory allocation.


### -param NameBuffer [out, optional]

Receives the symbol's name.  The name is qualified by the module to which the symbol belongs (for example, <b>mymodule!main</b>).  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the symbol's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Displacement [out, optional]

Receives the difference between the value of <i>Offset</i> and the base location of the symbol.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful.  However, the buffer was not large enough to hold the symbol's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No symbol could be found at the specified location.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols and symbol names, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548035">GetOffsetByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547204">GetNearNameByOffset</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::GetNameByOffset method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

