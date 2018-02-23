---
UID: NS:wdm._KBUGCHECK_DUMP_IO
title: "_KBUGCHECK_DUMP_IO"
author: windows-driver-content
description: The KBUGCHECK_DUMP_IO structure describes an I/O operation on the crash dump file.
old-location: kernel\kbugcheck_dump_io.htm
old-project: kernel
ms.assetid: d1c246bd-314d-475f-9df8-f1bf90355a5a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PKBUGCHECK_DUMP_IO, KBUGCHECK_DUMP_IO, KBUGCHECK_DUMP_IO structure [Kernel-Mode Driver Architecture], _KBUGCHECK_DUMP_IO, kstruct_c_a6201416-346e-4100-882c-329dd3ae1843.xml, kernel.kbugcheck_dump_io, PKBUGCHECK_DUMP_IO structure pointer [Kernel-Mode Driver Architecture], wdm/KBUGCHECK_DUMP_IO, wdm/PKBUGCHECK_DUMP_IO, PKBUGCHECK_DUMP_IO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KBUGCHECK_DUMP_IO
product: Windows
targetos: Windows
req.typenames: KBUGCHECK_DUMP_IO, *PKBUGCHECK_DUMP_IO
req.product: Windows 10 or later.
---

# _KBUGCHECK_DUMP_IO structure


## -description


The <b>KBUGCHECK_DUMP_IO</b> structure describes an I/O operation on the crash dump file.


## -syntax


````
typedef struct _KBUGCHECK_DUMP_IO {
  ULONG64                Offset;
  PVOID                  Buffer;
  ULONG                  BufferLength;
  KBUGCHECK_DUMP_IO_TYPE Type;
} KBUGCHECK_DUMP_IO, *PKBUGCHECK_DUMP_IO;
````


## -struct-fields




### -field Offset

Specifies the current offset in the crash dump file, or -1 if the crash dump file is being written sequentially.


### -field Buffer

Pointer to a buffer that contains the current data to be written to the dump file.


### -field BufferLength

Specifies the length of the buffer, in bytes, that is specified by the <b>Buffer</b> member.


### -field Type

Specifies the <a href="..\wdm\ne-wdm-_kbugcheck_dump_io_type.md">KBUGCHECK_DUMP_IO_TYPE</a> value that signifies the type of data to be written to the dump file.


## -remarks



For information about how this structure is used, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



<a href="..\wdm\ne-wdm-_kbugcheck_dump_io_type.md">KBUGCHECK_DUMP_IO_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_DUMP_IO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

