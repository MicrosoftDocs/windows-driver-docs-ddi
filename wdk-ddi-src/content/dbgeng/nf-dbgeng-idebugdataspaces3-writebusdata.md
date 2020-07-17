---
UID: NF:dbgeng.IDebugDataSpaces3.WriteBusData
title: IDebugDataSpaces3::WriteBusData (dbgeng.h)
description: The WriteBusData method writes data to a system bus.
old-location: debugger\writebusdata.htm
tech.root: debugger
ms.assetid: bd4e762d-b3d5-4a4c-bdeb-998cd72783b4
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces3::WriteBusData"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],WriteBusData method, IDebugDataSpaces2 interface [Windows Debugging],WriteBusData method, IDebugDataSpaces2::WriteBusData, IDebugDataSpaces3 interface [Windows Debugging],WriteBusData method, IDebugDataSpaces3.WriteBusData, IDebugDataSpaces3::WriteBusData, IDebugDataSpaces4 interface [Windows Debugging],WriteBusData method, IDebugDataSpaces4::WriteBusData, IDebugDataSpaces::WriteBusData, IDebugDataSpaces_a1fb8543-dee8-475d-b42c-17077d72b06e.xml, WriteBusData, WriteBusData method [Windows Debugging], WriteBusData method [Windows Debugging],IDebugDataSpaces interface, WriteBusData method [Windows Debugging],IDebugDataSpaces2 interface, WriteBusData method [Windows Debugging],IDebugDataSpaces3 interface, WriteBusData method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::WriteBusData, dbgeng/IDebugDataSpaces3::WriteBusData, dbgeng/IDebugDataSpaces4::WriteBusData, dbgeng/IDebugDataSpaces::WriteBusData, debugger.writebusdata
f1_keywords:
 - "dbgeng/IDebugDataSpaces.WriteBusData"
 - "IDebugDataSpaces.WriteBusData"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugDataSpaces.WriteBusData
- IDebugDataSpaces2.WriteBusData
- IDebugDataSpaces3.WriteBusData
- IDebugDataSpaces4.WriteBusData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces3::WriteBusData


## -description


The <b>WriteBusData</b> method writes data to a system bus.


## -parameters




### -param BusDataType [in]

Specifies the bus data type of the bus to write to.  For details of allowed values see the documentation for the BUS_DATA_TYPE enumeration in the Microsoft Windows SDK.


### -param BusNumber [in]

Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same bus data type.


### -param SlotNumber [in]

Specifies the logical slot number on the bus.


### -param Offset [in]

Specifies the offset in the bus data to start writing to.


### -param Buffer [in]

Specifies the data to write to the bus.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes written to the bus.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



This method is only available in kernel-mode debugging.

The nature of the data read from the bus is system, bus, and slot dependent.



