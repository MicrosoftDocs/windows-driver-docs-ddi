---
UID: NF:wdbgexts.WritePhysicalWithFlags
title: WritePhysicalWithFlags function (wdbgexts.h)
description: The WritePhysicalWithFlags function writes to physical memory.
old-location: debugger\writephysicalwithflags.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["WritePhysicalWithFlags function"]
ms.keywords: WdbgExts_Ref_7ef1e63e-87e2-4bf3-a432-78639684a18c.xml, WritePhysicalWithFlags, WritePhysicalWithFlags function [Windows Debugging], debugger.writephysicalwithflags, wdbgexts/WritePhysicalWithFlags
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
 - WritePhysicalWithFlags
 - wdbgexts/WritePhysicalWithFlags
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - WritePhysicalWithFlags
---

# WritePhysicalWithFlags function


## -description

The <b>WritePhysicalWithFlags</b> function writes to physical memory.

## -parameters

### -param address

Specifies the physical address to write.

### -param buf

Specifies the address of an array of bytes to hold the data that is  written.

### -param size

Specifies the number of bytes to write.

### -param flags

Specifies the properties of the physical memory to be written to.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
PHYS_FLAG_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>

### -param sizew

Receives the number of bytes actually written.

## -remarks

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-readphysicalwithflags">ReadPhysicalWithFlags</a>



<a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-writephysical">WritePhysical</a>
