---
UID: NS:wdm._KBUGCHECK_SECONDARY_DUMP_DATA
title: _KBUGCHECK_SECONDARY_DUMP_DATA (wdm.h)
description: The KBUGCHECK_SECONDARY_DUMP_DATA structure describes a section of driver-supplied data to be written by KbCallbackSecondaryDumpData routine to the crash dump file.
old-location: kernel\kbugcheck_secondary_dump_data.htm
tech.root: kernel
ms.assetid: dacb98cd-46bc-49d0-8ebd-29bb2dd5b713
ms.date: 05/08/2019
keywords: ["KBUGCHECK_SECONDARY_DUMP_DATA structure"]
ms.keywords: "*PKBUGCHECK_SECONDARY_DUMP_DATA, KBUGCHECK_SECONDARY_DUMP_DATA, KBUGCHECK_SECONDARY_DUMP_DATA structure [Kernel-Mode Driver Architecture], PKBUGCHECK_SECONDARY_DUMP_DATA, PKBUGCHECK_SECONDARY_DUMP_DATA structure pointer [Kernel-Mode Driver Architecture], _KBUGCHECK_SECONDARY_DUMP_DATA, kernel.kbugcheck_secondary_dump_data, kstruct_c_a9e0d726-41eb-4cf2-b2d4-c977be8750bb.xml, wdm/KBUGCHECK_SECONDARY_DUMP_DATA, wdm/PKBUGCHECK_SECONDARY_DUMP_DATA"
f1_keywords:
 - "wdm/KBUGCHECK_SECONDARY_DUMP_DATA"
 - "KBUGCHECK_SECONDARY_DUMP_DATA"
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
- KBUGCHECK_SECONDARY_DUMP_DATA
targetos: Windows
req.typenames: KBUGCHECK_SECONDARY_DUMP_DATA, *PKBUGCHECK_SECONDARY_DUMP_DATA
---

# _KBUGCHECK_SECONDARY_DUMP_DATA structure

## -description

The <b>KBUGCHECK_SECONDARY_DUMP_DATA</b> structure describes a section of driver-supplied data to be written by KbCallbackSecondaryDumpData routine to the crash dump file.

## -struct-fields

### -field InBuffer

Pointer to a buffer that is allocated by the system.

### -field InBufferLength

Specifies the size of the buffer, in bytes, specified by the <b>InBuffer</b> member.

### -field MaximumAllowed

Specifies the maximum amount of data that the KbCallbackSecondaryDumpData routine can write to the crash dump file.

### -field Guid

Specifies a GUID that identifies the driver's crash dump data. (Drivers must use unique GUIDs to mark their crash dump data. Use the GuidGen.exe tool to generate GUIDs for your driver. This tool is included in the Microsoft Windows SDK.)

### -field OutBuffer

Pointer to the buffer where the driver writes its crash dump data, or <b>NULL</b>.

### -field OutBufferLength

Specifies the size of the buffer, in bytes, that was specified by the <b>OutBuffer</b> member.

## -remarks

For more information about how this structure is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a> and [KBUGCHECK_REASON_CALLBACK_ROUTINE](nc-wdm-kbugcheck_reason_callback_routine.md) callback function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.
