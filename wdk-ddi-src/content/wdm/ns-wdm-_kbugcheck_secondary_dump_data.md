---
UID: NS:wdm._KBUGCHECK_SECONDARY_DUMP_DATA
title: _KBUGCHECK_SECONDARY_DUMP_DATA
author: windows-driver-content
description: The KBUGCHECK_SECONDARY_DUMP_DATA structure describes a section of driver-supplied data to be written by BugCheckSecondaryDumpDataCallback to the crash dump file.
old-location: kernel\kbugcheck_secondary_dump_data.htm
old-project: kernel
ms.assetid: dacb98cd-46bc-49d0-8ebd-29bb2dd5b713
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _KBUGCHECK_SECONDARY_DUMP_DATA, KBUGCHECK_SECONDARY_DUMP_DATA, *PKBUGCHECK_SECONDARY_DUMP_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KBUGCHECK_SECONDARY_DUMP_DATA
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: KBUGCHECK_SECONDARY_DUMP_DATA, *PKBUGCHECK_SECONDARY_DUMP_DATA
req.product: Windows 10 or later.
---

# _KBUGCHECK_SECONDARY_DUMP_DATA structure



## -description
The <b>KBUGCHECK_SECONDARY_DUMP_DATA</b> structure describes a section of driver-supplied data to be written by <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> to the crash dump file.



## -syntax

````
typedef struct _KBUGCHECK_SECONDARY_DUMP_DATA {
  PVOID InBuffer;
  ULONG InBufferLength;
  ULONG MaximumAllowed;
  GUID  Guid;
  PVOID OutBuffer;
  ULONG OutBufferLength;
} KBUGCHECK_SECONDARY_DUMP_DATA, *PKBUGCHECK_SECONDARY_DUMP_DATA;
````


## -struct-fields

### -field InBuffer

Pointer to a buffer that is allocated by the system.


### -field InBufferLength

Specifies the size of the buffer, in bytes, specified by the <b>InBuffer</b> member.


### -field MaximumAllowed

Specifies the maximum amount of data that the <i>BugCheckSecondaryDumpDataCallback</i> routine can write to the crash dump file.


### -field Guid

Specifies a GUID that identifies the driver's crash dump data. (Drivers must use unique GUIDs to mark their crash dump data. Use the GuidGen.exe tool to generate GUIDs for your driver. This tool is included in the Microsoft Windows SDK.)


### -field OutBuffer

Pointer to the buffer where the driver writes its crash dump data, or <b>NULL</b>.


### -field OutBufferLength

Specifies the size of the buffer, in bytes, that was specified by the <b>OutBuffer</b> member.


## -remarks
For more information about how this structure is used, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_SECONDARY_DUMP_DATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

