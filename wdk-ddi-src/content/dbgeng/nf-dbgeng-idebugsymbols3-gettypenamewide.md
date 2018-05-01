---
UID: NF:dbgeng.IDebugSymbols3.GetTypeNameWide
title: IDebugSymbols3::GetTypeNameWide
author: windows-driver-content
description: The GetTypeNameWide method returns the name of the type symbol specified by its type ID and module.
old-location: debugger\gettypenamewide.htm
old-project: debugger
ms.assetid: 0098aa2c-4ee4-49e4-a480-2402e771742f
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetTypeNameWide, GetTypeNameWide method [Windows Debugging], GetTypeNameWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetTypeNameWide method, IDebugSymbols3.GetTypeNameWide, IDebugSymbols3::GetTypeNameWide, dbgeng/IDebugSymbols3::GetTypeNameWide, debugger.gettypenamewide
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
-	IDebugSymbols3.GetTypeNameWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetTypeNameWide


## -description


The <b>GetTypeNameWide</b>  method returns the name of the type symbol specified by its type ID and module.


## -parameters




### -param Module [in]

Specifies the base address of the module to which the type belongs.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.


### -param TypeId [in]

Specifies the type ID of the type.


### -param NameBuffer [out, optional]

Receives the name of the type.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the type's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the buffer was not large enough to hold the name of the type and it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL </b></dt>
</dl>
</td>
<td width="60%">
The specified type could not be found in the specified module.

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

