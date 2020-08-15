---
UID: NF:wdm.MmAdvanceMdl
title: MmAdvanceMdl function (wdm.h)
description: The MmAdvanceMdl routine advances the beginning of an MDL's virtual memory range by the specified number of bytes.
old-location: kernel\mmadvancemdl.htm
tech.root: kernel
ms.assetid: 93e84c80-d671-4f04-8532-6c374e1ae72b
ms.date: 04/30/2018
keywords: ["MmAdvanceMdl function"]
ms.keywords: MmAdvanceMdl, MmAdvanceMdl routine [Kernel-Mode Driver Architecture], k106_14f78a97-f29c-4996-b8aa-94a04b62f11c.xml, kernel.mmadvancemdl, wdm/MmAdvanceMdl
f1_keywords:
 - "wdm/MmAdvanceMdl"
 - "MmAdvanceMdl"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmAdvanceMdl
targetos: Windows
req.typenames: 
---

# MmAdvanceMdl function


## -description


The <b>MmAdvanceMdl</b> routine advances the beginning of an MDL's virtual memory range by the specified number of bytes.


## -parameters




### -param Mdl 
[in, out]
Specifies the MDL to advance.


### -param NumberOfBytes 
[in]
Specifies the number of bytes to advance the beginning of the MDL.


## -returns



<b>MmAdvanceMdl</b> returns an NTSTATUS code. The possible return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully advanced the beginning of the MDL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The caller attempted to advance the beginning of the MDL past the end.

</td>
</tr>
</table>
 




## -remarks



<b>MmAdvanceMdl</b> advances only the beginning of the virtual memory address range. The ending address remains the same, and the length of the range is shrunk accordingly.

A higher-level driver can use <b>MmAdvanceMdl</b> under low-memory conditions when a lower-level driver can only partially complete a read/write request. The higher-level driver can use <b>MmAdvanceMdl</b> to advance past the part of the buffer that has already been read or written, and then reissue the IRP to complete the request. (The driver can, of course, repeat this process as many times as necessary.)

If <b>MmAdvanceMdl</b> advances past the initial page, any pages that <b>MmAdvanceMdl</b> passed are immediately unlocked, and the system virtual address that maps the MDL and the user address are also adjusted.

Use of <b>MmAdvanceMdl</b> can slow system performance. It must be used only when all of the following conditions hold:

<ul>
<li>
The higher-level driver, in its own I/O handling, can only complete certain I/O requests after transferring a fixed amount of data, but the lower-level driver only transfers data in smaller amounts. (An example is a network transport driver for the SPX or NBT protocols. Each protocol supports reliable message passing for messages that are bigger than one Ethernet frame. The transport driver can only complete a read request for such a message once it has reassembled the message from multiple Ethernet frames.)

</li>
<li>
The higher-level driver already tried and failed to allocate a new MDL to transfer a data fragment from an incomplete I/O request. (If the driver succeeds in allocating a new MDL, it must use that MDL and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl">IoBuildPartialMdl</a> to perform the I/O request instead of <b>MmAdvanceMdl</b>.)

</li>
<li>
The higher-level driver must continue to make progress, even under low-memory conditions.

</li>
</ul>
Drivers that do not satisfy these conditions must instead use the <b>IoBuildPartialMdl</b> routine to complete any partially-successful I/O operations.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl">IoBuildPartialMdl</a>
 

 

