---
UID: NE:wdm._KBUGCHECK_CALLBACK_REASON
title: _KBUGCHECK_CALLBACK_REASON (wdm.h)
description: The KBUGCHECK_CALLBACK_REASON enumeration type specifies the situations in which a bug-check callback executes.
old-location: kernel\kbugcheck_callback_reason.htm
tech.root: kernel
ms.assetid: 08246843-9b6e-4694-8475-acb02fbdd82b
ms.date: 05/06/2019
ms.keywords: KBUGCHECK_CALLBACK_REASON, KBUGCHECK_CALLBACK_REASON enumeration [Kernel-Mode Driver Architecture], KbCallbackAddPages, KbCallbackDumpIo, KbCallbackInvalid, KbCallbackReserved1, KbCallbackReserved2, KbCallbackSecondaryDumpData, _KBUGCHECK_CALLBACK_REASON, kernel.kbugcheck_callback_reason, sysenum_e8373f57-7ba5-44ad-9ad9-4110710732ee.xml, wdm/KBUGCHECK_CALLBACK_REASON, wdm/KbCallbackAddPages, wdm/KbCallbackDumpIo, wdm/KbCallbackInvalid, wdm/KbCallbackReserved1, wdm/KbCallbackReserved2 wdm/KbCallbackSecondaryDumpData
ms.topic: enum
f1_keywords:
 - "wdm/KBUGCHECK_CALLBACK_REASON"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Windows XP with Service Pack 1 (SP1), Windows Server 2003, and later versions of the Windows operating system.
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
- KBUGCHECK_CALLBACK_REASON
product:
- Windows
targetos: Windows
req.typenames: KBUGCHECK_CALLBACK_REASON
---

# _KBUGCHECK_CALLBACK_REASON enumeration

## -description

The <b>KBUGCHECK_CALLBACK_REASON</b> enumeration type specifies the situations in which a bug-check callback executes.

## -enum-fields

### -field KbCallbackInvalid
Reserved for system use. Do not use.

### -field KbCallbackReserved1

Reserved for system use. Do not use.

### -field KbCallbackSecondaryDumpData

The callback function provides data to append to the secondary data area of the crash dump file when the system issues a bug check. For more information about this type of callback, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine#implementing-a-kbcallbacksecondarydumpdata-callback-routine">Implementing a KbCallbackSecondaryDumpData Callback Routine</a>.

### -field KbCallbackDumpIo

Specifies that the system should call the callback function each time it writes data to a crash dump file. Drivers for devices that monitor the system state can use this type of callback. For more information about this type of callback, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine#implementing-a-kbcallbackdumpio-callback-routine">Implementing a KbCallbackDumpIo Callback Routine</a>.

### -field KbCallbackAddPages

The callback function adds one or more pages of driver-specific data to the primary section of the crash dump file when the operating system issues a bug check. For more information about this type of callback, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine#implementing-a-kbcallbackaddpages-callback-routine">Implementing a KbCallbackAddPages Callback Routine</a>.

### -field KbCallbackSecondaryMultiPartDumpData

Specifies that the callback is executed to get the amount of data the driver wants to store in the dump file. This enumeration value is supported in Windows Server 2008 and later versions of Windows.

### -field KbCallbackRemovePages

The callback function removes one or more pages of driver-supplied data from the crash dump file. For more information, see <b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_kbugcheck_remove_pages">KBUGCHECK_REMOVE_PAGES</a></b>.

### -field KbCallbackTriageDumpData

Specifies that the callback is executed to add virtual memory ranges the driver wants to preserve in the carved minidump file. This enumeration value is supported starting in Windows 10, version 1809 and Windows Server 2019. For more information about this type of callback, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine#implementing-a-kbcallbacktriagedumpdata-callback-routine">Implementing a KbCallbackTriageDumpData Callback Routine</a>.

### -field KbCallbackReserved2

Reserved for system use. Do not use.

## -remarks

A driver uses this enumeration to specify the type of [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine to register when it calls the [**KeRegisterBugCheckReasonCallback**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback) function.

For information about how this enumeration is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a>
