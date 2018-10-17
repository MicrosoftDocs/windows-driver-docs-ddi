---
UID: NF:dbgeng.IDebugSymbols3.GetOffsetTypeId
title: IDebugSymbols3::GetOffsetTypeId
author: windows-driver-content
description: The GetOffsetTypeId method returns the type ID of the symbol closest to the specified memory location.
old-location: debugger\getoffsettypeid.htm
tech.root: debugger
ms.assetid: cf533f21-90eb-46ec-860f-d12a8d40c430
ms.date: 5/3/2018
ms.keywords: GetOffsetTypeId, GetOffsetTypeId method [Windows Debugging], GetOffsetTypeId method [Windows Debugging],IDebugSymbols interface, GetOffsetTypeId method [Windows Debugging],IDebugSymbols2 interface, GetOffsetTypeId method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetOffsetTypeId method, IDebugSymbols2 interface [Windows Debugging],GetOffsetTypeId method, IDebugSymbols2::GetOffsetTypeId, IDebugSymbols3 interface [Windows Debugging],GetOffsetTypeId method, IDebugSymbols3.GetOffsetTypeId, IDebugSymbols3::GetOffsetTypeId, IDebugSymbols::GetOffsetTypeId, IDebugSymbols_3f41981b-8ed2-4828-8bfb-a50b934a65ee.xml, dbgeng/IDebugSymbols2::GetOffsetTypeId, dbgeng/IDebugSymbols3::GetOffsetTypeId, dbgeng/IDebugSymbols::GetOffsetTypeId, debugger.getoffsettypeid
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
-	IDebugSymbols.GetOffsetTypeId
-	IDebugSymbols2.GetOffsetTypeId
-	IDebugSymbols3.GetOffsetTypeId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetOffsetTypeId


## -description


The <b>GetOffsetTypeId</b> method returns the type ID of the symbol closest to the specified memory location.


## -parameters




### -param Offset [in]

Specifies the location in the target's memory for the symbol.  The symbol closest to this location is used.


### -param TypeId [out]

Receives the type ID of the symbol.


### -param Module [out, optional]

Specifies the location in the target's memory address space of the base of the module to which the symbol belongs.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful

</td>
</tr>
</table>
 




## -remarks



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549173">GetSymbolTypeId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549376">GetTypeId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

