---
UID: NE:wdm._KBUGCHECK_DUMP_IO_TYPE
title: _KBUGCHECK_DUMP_IO_TYPE (wdm.h)
description: The KBUGCHECK_DUMP_IO_TYPE enumeration type identifies the type of a section of data within a crash dump file.
old-location: kernel\kbugcheck_dump_io_type.htm
tech.root: kernel
ms.assetid: 928be338-a588-4535-8395-229ec6f3ecb7
ms.date: 05/02/2019
ms.keywords: KBUGCHECK_DUMP_IO_TYPE, KBUGCHECK_DUMP_IO_TYPE enumeration [Kernel-Mode Driver Architecture], KbDumpIoBody, KbDumpIoComplete, KbDumpIoHeader, KbDumpIoInvalid, KbDumpIoSecondaryData, _KBUGCHECK_DUMP_IO_TYPE, kernel.kbugcheck_dump_io_type, sysenum_e6f9d577-edd8-43f0-9cc5-33b88e5237aa.xml, wdm/KBUGCHECK_DUMP_IO_TYPE, wdm/KbDumpIoBody, wdm/KbDumpIoComplete, wdm/KbDumpIoHeader, wdm/KbDumpIoInvalid, wdm/KbDumpIoSecondaryData
ms.topic: enum
f1_keywords:
 - "wdm/KBUGCHECK_DUMP_IO_TYPE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- KBUGCHECK_DUMP_IO_TYPE
product:
- Windows
targetos: Windows
req.typenames: KBUGCHECK_DUMP_IO_TYPE
---

# _KBUGCHECK_DUMP_IO_TYPE enumeration

## -description

The <b>KBUGCHECK_DUMP_IO_TYPE</b> enumeration type identifies the type of a section of data within a crash dump file.

## -enum-fields

### -field KbDumpIoInvalid

Reserved for system use. Do not use.

### -field KbDumpIoHeader

Specifies that crash dump data is header information.

### -field KbDumpIoBody

Specifies that the crash dump data is part of the main body of the crash dump, such as the memory state at the time of the bug check.

### -field KbDumpIoSecondaryData

Specifies that the crash dump data is data returned by a KbCallbackSecondaryDumpData routine.

### -field KbDumpIoComplete

Specifies that the crash dump data has been completely written.

## -remarks

<b>KBUGCHECK_DUMP_IO_TYPE</b> values are used in the <b>Type</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_kbugcheck_dump_io">KBUGCHECK_DUMP_IO</a> to specify the type of data in an I/O operation on the crash dump file.

 For more information about this type of callback, see "Implementing KbCallbackDumpIo Callback Routine" in <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_kbugcheck_dump_io">KBUGCHECK_DUMP_IO</a>
