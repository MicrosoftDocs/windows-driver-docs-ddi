---
UID: NE:wdm._KBUGCHECK_DUMP_IO_TYPE
title: "_KBUGCHECK_DUMP_IO_TYPE"
author: windows-driver-content
description: The KBUGCHECK_DUMP_IO_TYPE enumeration type identifies the type of a section of data within a crash dump file.
old-location: kernel\kbugcheck_dump_io_type.htm
old-project: kernel
ms.assetid: 928be338-a588-4535-8395-229ec6f3ecb7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KbDumpIoBody, wdm/KBUGCHECK_DUMP_IO_TYPE, KbDumpIoBody, wdm/KbDumpIoSecondaryData, KbDumpIoHeader, wdm/KbDumpIoComplete, wdm/KbDumpIoInvalid, _KBUGCHECK_DUMP_IO_TYPE, KbDumpIoComplete, sysenum_e6f9d577-edd8-43f0-9cc5-33b88e5237aa.xml, KBUGCHECK_DUMP_IO_TYPE enumeration [Kernel-Mode Driver Architecture], KbDumpIoSecondaryData, wdm/KbDumpIoHeader, KbDumpIoInvalid, KBUGCHECK_DUMP_IO_TYPE, kernel.kbugcheck_dump_io_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KBUGCHECK_DUMP_IO_TYPE
product: Windows
targetos: Windows
req.typenames: KBUGCHECK_DUMP_IO_TYPE
req.product: Windows 10 or later.
---

# _KBUGCHECK_DUMP_IO_TYPE enumeration


## -description


The <b>KBUGCHECK_DUMP_IO_TYPE</b> enumeration type identifies the type of a section of data within a crash dump file.


## -syntax


````
typedef enum _KBUGCHECK_DUMP_IO_TYPE { 
  KbDumpIoInvalid        = 0,
  KbDumpIoHeader         = 1,
  KbDumpIoBody           = 2,
  KbDumpIoSecondaryData  = 3,
  KbDumpIoComplete       = 4
} KBUGCHECK_DUMP_IO_TYPE;
````


## -enum-fields




### -field KbDumpIoInvalid

Reserved for system use. Do not use.


### -field KbDumpIoHeader

Specifies that crash dump data is header information.


### -field KbDumpIoBody

Specifies that the crash dump data is part of the main body of the crash dump, such as the memory state at the time of the bug check.


### -field KbDumpIoSecondaryData

Specifies that the crash dump data is data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> routine.


### -field KbDumpIoComplete

Specifies that the crash dump data has been completely written.


## -remarks



<b>KBUGCHECK_DUMP_IO_TYPE</b> values are used in the <b>Type</b> member of <a href="..\wdm\ns-wdm-_kbugcheck_dump_io.md">KBUGCHECK_DUMP_IO</a> to specify the type of data in an I/O operation on the crash dump file.

For more information about how this enumeration type is used, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>



<a href="..\wdm\ns-wdm-_kbugcheck_dump_io.md">KBUGCHECK_DUMP_IO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_DUMP_IO_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

