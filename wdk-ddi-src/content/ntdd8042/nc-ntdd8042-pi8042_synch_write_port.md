---
UID: NC:ntdd8042.PI8042_SYNCH_WRITE_PORT
title: PI8042_SYNCH_WRITE_PORT (ntdd8042.h)
description: The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.
old-location: hid\pi8042_synch_write_port.htm
tech.root: hid
ms.assetid: f4b0642c-0355-46ae-9c23-fc9c98dfaf21
ms.date: 04/30/2018
keywords: ["PI8042_SYNCH_WRITE_PORT callback function"]
ms.keywords: PI8042_SYNCH_WRITE_PORT, PI8042_SYNCH_WRITE_PORT callback, SynchWritePort, SynchWritePort callback function [Human Input Devices], hid.pi8042_synch_write_port, i8042ref_79e22dfb-4844-4126-a6a2-b2f908cbdf79.xml, ntdd8042/SynchWritePort
f1_keywords:
 - "ntdd8042/SynchWritePort"
 - "SynchWritePort"
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ntdd8042.h
api_name:
- SynchWritePort
targetos: Windows
req.typenames: 
---

# PI8042_SYNCH_WRITE_PORT callback function


## -description


The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.


## -parameters




### -param Context 
[in]
Pointer to a context supplied by I8042prt. 


### -param Value 
[in]
Specifies the UCHAR value to write to an i8042 port.


### -param WaitForACK 
[in]
Specifies, if <b>TRUE</b>, that the routine waits until the write is acknowledged by the i8042 port. Otherwise, the routine returns without waiting for an acknowledgment from the port.


## -returns



The PI8042_SYNCH_WRITE_PORT callback returns one of the following status values:

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
The routine successfully wrote a byte to an i8042 port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The hardware was not ready for a write access.

</td>
</tr>
</table>
 




## -remarks



The PI8042_SYNCH_READ_PORT callback can only be used in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_keyboard_initialization_routine">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a> callback. I8042prt specifies the write port callback in the <i>WritePort</i> parameter that I8042prt inputs to a keyboard initialization routine.

The routine polls the hardware until a read is returned by the hardware or an internal time-out occurs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_keyboard_initialization_routine">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/nc-ntdd8042-pi8042_synch_read_port">PI8042_SYNCH_READ_PORT</a>
 

 

