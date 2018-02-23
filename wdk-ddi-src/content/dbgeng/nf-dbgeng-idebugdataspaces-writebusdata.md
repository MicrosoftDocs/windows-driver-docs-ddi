---
UID: NF:dbgeng.IDebugDataSpaces.WriteBusData
title: IDebugDataSpaces::WriteBusData method
author: windows-driver-content
description: The WriteBusData method writes data to a system bus.
old-location: debugger\writebusdata.htm
old-project: Debugger
ms.assetid: bd4e762d-b3d5-4a4c-bdeb-998cd72783b4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: WriteBusData method [Windows Debugging], IDebugDataSpaces_a1fb8543-dee8-475d-b42c-17077d72b06e.xml, IDebugDataSpaces interface [Windows Debugging], WriteBusData method, dbgeng/IDebugDataSpaces4::WriteBusData, IDebugDataSpaces4::WriteBusData, dbgeng/IDebugDataSpaces2::WriteBusData, WriteBusData method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces3::WriteBusData, WriteBusData, IDebugDataSpaces2::WriteBusData, dbgeng/IDebugDataSpaces::WriteBusData, debugger.writebusdata, IDebugDataSpaces4 interface [Windows Debugging], WriteBusData method, IDebugDataSpaces, IDebugDataSpaces2 interface [Windows Debugging], WriteBusData method, IDebugDataSpaces::WriteBusData, WriteBusData method [Windows Debugging], IDebugDataSpaces2 interface, dbgeng/IDebugDataSpaces3::WriteBusData, IDebugDataSpaces3 interface [Windows Debugging], WriteBusData method, WriteBusData method [Windows Debugging], IDebugDataSpaces3 interface, WriteBusData method [Windows Debugging], IDebugDataSpaces4 interface
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
-	IDebugDataSpaces.WriteBusData
-	IDebugDataSpaces2.WriteBusData
-	IDebugDataSpaces3.WriteBusData
-	IDebugDataSpaces4.WriteBusData
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces::WriteBusData method


## -description


The <b>WriteBusData</b> method writes data to a system bus.


## -syntax


````
HRESULT WriteBusData(
  [in]            ULONG  BusDataType,
  [in]            ULONG  BusNumber,
  [in]            ULONG  SlotNumber,
  [in]            ULONG  Offset,
  [in]            PVOID  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG BytesWritten
);
````


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



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



