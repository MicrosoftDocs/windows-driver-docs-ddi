---
UID: NS:ntddtape._TAPE_PREPARE
title: _TAPE_PREPARE (ntddtape.h)
description: The TAPE_PREPARE structure is used in conjunction with the IOCTL_TAPE_PREPARE request to load or unload tape, reset the tape's tension, lock or unlock the ejection mechanism, or format the tape.
old-location: storage\tape_prepare.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TAPE_PREPARE structure"]
ms.keywords: "*PTAPE_PREPARE, PTAPE_PREPARE, PTAPE_PREPARE structure pointer [Storage Devices], TAPE_PREPARE, TAPE_PREPARE structure [Storage Devices], _TAPE_PREPARE, ntddtape/PTAPE_PREPARE, ntddtape/TAPE_PREPARE, storage.tape_prepare, structs-tape_b563ea19-797c-4df0-a384-7e9c579ee2e9.xml"
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
req.target-type: Windows
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
req.typenames: TAPE_PREPARE, *PTAPE_PREPARE
f1_keywords:
 - _TAPE_PREPARE
 - ntddtape/_TAPE_PREPARE
 - PTAPE_PREPARE
 - ntddtape/PTAPE_PREPARE
 - TAPE_PREPARE
 - ntddtape/TAPE_PREPARE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddtape.h
api_name:
 - _TAPE_PREPARE
 - PTAPE_PREPARE
 - TAPE_PREPARE
---

# _TAPE_PREPARE structure (ntddtape.h)


## -description

The TAPE_PREPARE structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_prepare">IOCTL_TAPE_PREPARE</a> request to load or unload tape, reset the tape's tension, lock or unlock the ejection mechanism, or format the tape.

## -struct-fields

### -field Operation

Indicates the type of operation to perform. This member can be one of the following:

<table>
<tr>
<th>Operation</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TAPE_LOAD

</td>
<td>
Loads the tape and moves the tape to the beginning. 

</td>
</tr>
<tr>
<td>
TAPE_UNLOAD

</td>
<td>
Moves the tape to the beginning for removal from the device. After a successful unload operation, the device returns errors to applications that attempt to access the tape, until the tape is loaded again. 

</td>
</tr>
<tr>
<td>
TAPE_TENSION

</td>
<td>
Adjusts the tension by moving the tape to the end of the tape and back to the beginning. This option is not supported by all devices. This value is ignored if it is not supported.

</td>
</tr>
<tr>
<td>
TAPE_LOCK

</td>
<td>
Locks the tape ejection mechanism, so that the tape is not ejected accidentally. 

</td>
</tr>
<tr>
<td>
TAPE_UNLOCK

</td>
<td>
Unlocks the tape ejection mechanism. 

</td>
</tr>
<tr>
<td>
TAPE_FORMAT

</td>
<td>
Performs a low-level format of the tape. Not all devices support this feature. This value is ignored if it is not supported.

</td>
</tr>
</table>

### -field Immediate

When set to <b>TRUE</b>, indicates that the target device should return status immediately. When set to <b>FALSE</b>, indicates that the device should return status after the operation is complete.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_prepare">IOCTL_TAPE_PREPARE</a>



<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniPrepare</a>

