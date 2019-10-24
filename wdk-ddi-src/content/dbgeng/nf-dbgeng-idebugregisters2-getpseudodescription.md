---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoDescription
title: IDebugRegisters2::GetPseudoDescription (dbgeng.h)
description: The GetPseudoDescription method returns a description of a pseudo-register, including its name and type.
old-location: debugger\getpseudodescription.htm
tech.root: debugger
ms.assetid: dc1c7b8a-1233-4f22-8c5f-273f370a1e06
ms.date: 05/03/2018
ms.keywords: GetPseudoDescription, GetPseudoDescription method [Windows Debugging], GetPseudoDescription method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetPseudoDescription method, IDebugRegisters2.GetPseudoDescription, IDebugRegisters2::GetPseudoDescription, IDebugRegisters_7b1f8069-32d0-4fb4-9cee-7fd045bae8d3.xml, dbgeng/IDebugRegisters2::GetPseudoDescription, debugger.getpseudodescription
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugRegisters2.GetPseudoDescription"
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
- IDebugRegisters2.GetPseudoDescription
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::GetPseudoDescription


## -description


The <b>GetPseudoDescription</b>  method returns a description of a pseudo-register, including its name and type.


## -parameters




### -param Register [in]

Specifies the index of the pseudo-register whose description is requested.  The index is always between zero and the number of pseudo-registers (returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getnumberpseudoregisters">GetNumberPseudoRegisters</a>) minus one.


### -param NameBuffer [out, optional]

Receives the name of the pseudo-register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size, in characters, of the buffer that <i>NameBuffer </i>specifies.


### -param NameSize [out, optional]

Receives the size in characters of the name of the pseudo-register.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param TypeModule [out, optional]

Receives the base address of the module to which the register's type belongs.  If the type of the register is not known, zero is returned.  If <i>TypeModule</i> is <b>NULL</b>, no information is returned.


### -param TypeId [out, optional]

Receives the type ID of the type within the module returned in <i>TypeModule</i>.  If the type ID is not known, zero is returned.  If <i>TypeId</i> is <b>NULL</b>, no information is returned.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The description for the register was not available

</td>
</tr>
</table>
 




## -remarks



Descriptions are not always available for all registers.  If a pseudo-register does not have a value - for example, <b>$eventip</b> will not have a value before an event has occurred - or a type cannot be determined for a pseudo-register, this method will return E_FAIL.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getnumberpseudoregisters">GetNumberPseudoRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getpseudoindexbyname">GetPseudoIndexByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>
 

 

