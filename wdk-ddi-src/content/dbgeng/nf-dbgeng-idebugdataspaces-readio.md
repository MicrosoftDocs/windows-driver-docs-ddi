---
UID: NF:dbgeng.IDebugDataSpaces.ReadIo
title: IDebugDataSpaces::ReadIo (dbgeng.h)
description: The ReadIo method reads from the system and bus I/O memory.
old-location: debugger\readio.htm
tech.root: debugger
ms.assetid: d690cf53-63a6-487c-a952-07035786d19c
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces::ReadIo"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadIo method, IDebugDataSpaces.ReadIo, IDebugDataSpaces2 interface [Windows Debugging],ReadIo method, IDebugDataSpaces2::ReadIo, IDebugDataSpaces3 interface [Windows Debugging],ReadIo method, IDebugDataSpaces3::ReadIo, IDebugDataSpaces4 interface [Windows Debugging],ReadIo method, IDebugDataSpaces4::ReadIo, IDebugDataSpaces::ReadIo, IDebugDataSpaces_a6189a47-dc48-44cf-aadd-61769085ebc5.xml, ReadIo, ReadIo method [Windows Debugging], ReadIo method [Windows Debugging],IDebugDataSpaces interface, ReadIo method [Windows Debugging],IDebugDataSpaces2 interface, ReadIo method [Windows Debugging],IDebugDataSpaces3 interface, ReadIo method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadIo, dbgeng/IDebugDataSpaces3::ReadIo, dbgeng/IDebugDataSpaces4::ReadIo, dbgeng/IDebugDataSpaces::ReadIo, debugger.readio
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugDataSpaces::ReadIo
 - dbgeng/IDebugDataSpaces::ReadIo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces.ReadIo
 - IDebugDataSpaces2.ReadIo
 - IDebugDataSpaces3.ReadIo
 - IDebugDataSpaces4.ReadIo
---

# IDebugDataSpaces::ReadIo


## -description

The <b>ReadIo</b> method reads from the system and bus I/O memory.

## -parameters

### -param InterfaceType 

[in]
Specifies the interface type of the I/O bus.  This parameter may take values in the INTERFACE_TYPE enumeration defined in wdm.h.

### -param BusNumber 

[in]
Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same interface type.

### -param AddressSpace 

[in]
This parameter must be equal to one.

### -param Offset 

[in]
Specifies the I/O address within the address space.

### -param Buffer 

[out]
Receives the data read from the I/O bus.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.  At present, this must be 1, 2, or 4.

### -param BytesRead 

[out, optional]
Receives the number of bytes returned read from the I/O bus.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.

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
</table>
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in kernel-mode debugging.

