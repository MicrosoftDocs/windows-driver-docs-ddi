---
UID: NF:dbgeng.IDebugSymbols3.GetConstantName
title: IDebugSymbols3::GetConstantName method
author: windows-driver-content
description: The GetConstantName method returns the name of the specified constant.
old-location: debugger\getconstantname.htm
old-project: Debugger
ms.assetid: bb308ee7-e8bc-49c0-b1f9-199af7dca289
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetConstantName method [Windows Debugging], GetConstantName, debugger.getconstantname, GetConstantName method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3::GetConstantName, GetConstantName method [Windows Debugging], IDebugSymbols2 interface, dbgeng/IDebugSymbols3::GetConstantName, IDebugSymbols2::GetConstantName, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetConstantName method, dbgeng/IDebugSymbols2::GetConstantName, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], GetConstantName method, IDebugSymbols_438111b4-a0f4-40cc-aadc-8b1d2c67b219.xml
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
-	IDebugSymbols2.GetConstantName
-	IDebugSymbols3.GetConstantName
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetConstantName method


## -description


The <b>GetConstantName</b>  method returns the name of the specified constant.


## -syntax


````
HRESULT GetConstantName(
  [in]            ULONG64 Module,
  [in]            ULONG   TypeId,
  [in]            ULONG64 Value,
  [out, optional] PSTR    NameBuffer,
  [in]            ULONG   NameBufferSize,
  [out, optional] PULONG  NameSize
);
````


## -parameters




### -param Module [in]

Specifies the base address of the module in which the constant was defined.


### -param TypeId [in]

Specifies the type ID of the constant.


### -param Value [in]

Specifies the value of the constant.


### -param NameBuffer [out, optional]

Receives the constant's name.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the constant's name.


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
The method was successful. However, the buffer was not large enough for the constant's name and it was truncated.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.



