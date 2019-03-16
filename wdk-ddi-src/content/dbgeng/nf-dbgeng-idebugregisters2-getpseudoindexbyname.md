---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoIndexByName
title: IDebugRegisters2::GetPseudoIndexByName (dbgeng.h)
description: The GetPseudoIndexByName method returns the index of a pseudo-register.
old-location: debugger\getpseudoindexbyname.htm
tech.root: debugger
ms.assetid: 0973d8d8-53df-47aa-be65-71045c2e6006
ms.date: 05/03/2018
ms.keywords: GetPseudoIndexByName, GetPseudoIndexByName method [Windows Debugging], GetPseudoIndexByName method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetPseudoIndexByName method, IDebugRegisters2.GetPseudoIndexByName, IDebugRegisters2::GetPseudoIndexByName, IDebugRegisters_95580025-4059-4a5b-bd68-d7ebfa20607e.xml, dbgeng/IDebugRegisters2::GetPseudoIndexByName, debugger.getpseudoindexbyname
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugRegisters2.GetPseudoIndexByName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::GetPseudoIndexByName


## -description


The <b>GetPseudoIndexByName</b>  method returns the index of a pseudo-register.


## -parameters




### -param Name [in]

Specifies the name of the pseudo-register whose index is requested.  The name includes the leading dollar sign ( <b>$</b> ), for example, "$frame".


### -param Index [out]

Receives the index of the pseudo-register.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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
</table>
 




## -remarks



For the names of all the pseudo-registers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553485">Pseudo-Register Syntax</a>.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548189">GetPseudoDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>
 

 

