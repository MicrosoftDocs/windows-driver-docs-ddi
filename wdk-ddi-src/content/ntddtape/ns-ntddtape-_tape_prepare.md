---
UID: NS:ntddtape._TAPE_PREPARE
title: "_TAPE_PREPARE"
author: windows-driver-content
description: The TAPE_PREPARE structure is used in conjunction with the IOCTL_TAPE_PREPARE request to load or unload tape, reset the tape's tension, lock or unlock the ejection mechanism, or format the tape.
old-location: storage\tape_prepare.htm
old-project: storage
ms.assetid: 0bca5849-e0f9-42b2-82f8-aadea2aa01ae
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PTAPE_PREPARE, ,, A, E, P, PTAPE_PREPARE, PTAPE_PREPARE structure pointer [Storage Devices], R, T, TAPE_PREPARE, TAPE_PREPARE structure [Storage Devices], _, _TAPE_PREPARE, ntddtape/PTAPE_PREPARE, ntddtape/TAPE_PREPARE, storage.tape_prepare, structs-tape_b563ea19-797c-4df0-a384-7e9c579ee2e9.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddtape.h
apiname:
-	TAPE_PREPARE
product: Windows
targetos: Windows
req.typenames: TAPE_PREPARE, *PTAPE_PREPARE
---

# _TAPE_PREPARE structure


## -description


The TAPE_PREPARE structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl_tape_prepare.md">IOCTL_TAPE_PREPARE</a> request to load or unload tape, reset the tape's tension, lock or unlock the ejection mechanism, or format the tape.


## -syntax


````
typedef struct _TAPE_PREPARE {
  ULONG   Operation;
  BOOLEAN Immediate;
} TAPE_PREPARE, *PTAPE_PREPARE;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567950">TapeMiniPrepare</a>



<a href="..\ntddtape\ni-ntddtape-ioctl_tape_prepare.md">IOCTL_TAPE_PREPARE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_PREPARE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

