---
UID: NF:dbgeng.IDebugDataSpaces4.WritePhysical2
title: IDebugDataSpaces4::WritePhysical2 (dbgeng.h)
description: The WritePhysical2 method writes data to the specified physical address in the target's memory.
old-location: debugger\writephysical2.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::WritePhysical2"]
ms.keywords: IDebugDataSpaces4 interface [Windows Debugging],WritePhysical2 method, IDebugDataSpaces4.WritePhysical2, IDebugDataSpaces4::WritePhysical2, IDebugDataSpaces_bc084790-b047-4257-b7fd-578fd4454747.xml, WritePhysical2, WritePhysical2 method [Windows Debugging], WritePhysical2 method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces4::WritePhysical2, debugger.writephysical2
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
 - IDebugDataSpaces4::WritePhysical2
 - dbgeng/IDebugDataSpaces4::WritePhysical2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces4.WritePhysical2
---

# IDebugDataSpaces4::WritePhysical2


## -description

The <b>WritePhysical2</b> method writes data to the specified physical address in the target's memory.

## -parameters

### -param Offset 

[in]
Specifies the physical address of the memory to write the data to.

### -param Flags 

[in]
Specifies the properties of the physical memory to be written to.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>

### -param Buffer 

[in]
Specifies the data to write.

### -param BufferSize 

[in]
Specifies the size, in bytes, of the <i>Buffer</i> buffer.  This is the maximum number of bytes that will be written.

### -param BytesWritten 

[out, optional]
Receives the number of bytes written to the target's memory.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The flags DEBUG_PHYSICAL_CACHED, DEBUG_PHYSICAL_UNCACHED, and DEBUG_PHYSICAL_WRITE_COMBINED can only be used when the target is a live kernel target that is being debugged in the standard way (using a COM port, 1394 bus, or named pipe).

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writephysical">WritePhysical</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writephysical2">WritePhysical2</a>
