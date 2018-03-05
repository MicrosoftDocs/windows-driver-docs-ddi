---
UID: NF:dbgeng.IDebugSymbolGroup.GetSymbolName
title: IDebugSymbolGroup::GetSymbolName method
author: windows-driver-content
description: The GetSymbolName method returns the name of a symbol in a symbol group.
old-location: debugger\getsymbolname.htm
old-project: debugger
ms.assetid: a594e436-3b37-4bba-ba9d-65159fdfb7ac
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ComOther_e12d7aee-985e-4770-8567-7c3748a79905.xml, GetSymbolName method [Windows Debugging], GetSymbolName method [Windows Debugging], IDebugSymbolGroup interface, GetSymbolName method [Windows Debugging], IDebugSymbolGroup2 interface, GetSymbolName,IDebugSymbolGroup.GetSymbolName, IDebugSymbolGroup, IDebugSymbolGroup interface [Windows Debugging], GetSymbolName method, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolName method, IDebugSymbolGroup2::GetSymbolName, IDebugSymbolGroup::GetSymbolName, dbgeng/IDebugSymbolGroup2::GetSymbolName, dbgeng/IDebugSymbolGroup::GetSymbolName, debugger.getsymbolname
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
-	dbgeng.h
api_name:
-	IDebugSymbolGroup.GetSymbolName
-	IDebugSymbolGroup2.GetSymbolName
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup::GetSymbolName method


## -description


The <b>GetSymbolName</b>  method returns the name of a symbol in a symbol group.


## -syntax


````
HRESULT GetSymbolName(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
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

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::GetSymbolName method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

