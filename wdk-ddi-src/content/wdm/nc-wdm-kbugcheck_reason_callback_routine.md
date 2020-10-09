---
UID: NC:wdm.KBUGCHECK_REASON_CALLBACK_ROUTINE
title: KBUGCHECK_REASON_CALLBACK_ROUTINE (wdm.h)
description: Driver-implemented callback functions that the system executes when it issues a bug check.
old-location: kernel\bugcheckaddpagescallback.htm
tech.root: kernel
ms.assetid: a3d33a3a-efe7-4346-82bc-555c57ae7b74
ms.date: 05/02/2019
keywords: ["KBUGCHECK_REASON_CALLBACK_ROUTINE callback function"]
ms.keywords: BugCheckAddPagesCallback, BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, DrvrRtns_337f5b60-9ed5-4a1b-a215-1d3b1e3abb1e.xml, KBUGCHECK_REASON_CALLBACK_ROUTINE, KBUGCHECK_REASON_CALLBACK_ROUTINE callback, MyBugCheckCallback, MyBugCheckCallback callback function [Kernel-Mode Driver Architecture], kernel.bugcheckaddpagescallback, wdm/MyBugCheckCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows Server 2008.
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
req.irql: Called at HIGH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - KBUGCHECK_REASON_CALLBACK_ROUTINE
 - wdm/KBUGCHECK_REASON_CALLBACK_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - MyBugCheckCallback
---

# KBUGCHECK_REASON_CALLBACK_ROUTINE callback function


## -description

Driver-implemented callback functions that the system executes when it issues a bug check.

See [**KBUGCHECK_CALLBACK_REASON**](./ne-wdm-_kbugcheck_callback_reason.md) for information on available callback types.

## -parameters

### -param Reason 

[in]
An enumeration of type [**KBUGCHECK_CALLBACK_REASON**](./ne-wdm-_kbugcheck_callback_reason.md) that specifies the reason for the call to the callback routine.

### -param Record 

[in]
A pointer to the [**KBUGCHECK_REASON_CALLBACK_RECORD**](./ns-wdm-_kbugcheck_reason_callback_record.md) structure that the driver supplied when it registered this callback. For more information, see the description of the <i>CallbackRecord</i> parameter in [**KeRegisterBugCheckReasonCallback**](./nf-wdm-keregisterbugcheckreasoncallback.md).

### -param ReasonSpecificData 

[in, out]
Pointer to a buffer that contains a structure of type determined by the table below. Certain members of this structure are filled in by the operating system before it calls the callback routine, and other members must be filled in by the callback routine. For more information, see <a href="/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

|Value|Data Structure|
|--- |--- |
|**KbCallbackSecondaryDumpData**|[**KBUGCHECK_SECONDARY_DUMP_DATA**](./ns-wdm-_kbugcheck_secondary_dump_data.md)|
|**KbCallbackDumpIo**|[**KBUGCHECK_DUMP_IO**](./ns-wdm-_kbugcheck_dump_io.md)|
|**KbCallbackAddPages**|[**KBUGCHECK_ADD_PAGES**](./ns-wdm-_kbugcheck_add_pages.md)|
|**KbCallbackSecondaryMultiPartDumpData**|[**KBUGCHECK_SECONDARY_DUMP_DATA_EX**](./ns-wdm-_kbugcheck_secondary_dump_data_ex.md)|
|**KbCallbackRemovePages**|[**KBUGCHECK_REMOVE_PAGES**](./ns-wdm-_kbugcheck_remove_pages.md)|
|**KbCallbackTriageDumpData**|[**KBUGCHECK_TRIAGE_DUMP_DATA**](./ns-wdm-_kbugcheck_triage_dump_data.md)|

### -param ReasonSpecificDataLength 

[in]
Specifies the size, in bytes, of the buffer that the <i>ReasonSpecificData</i> parameter points to.

## -remarks

For information about how to implement this callback routine, see <a href="/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

For sample code that shows how to write data to the crash dump file, see [DMF_CrashDump](https://github.com/Microsoft/DMF/blob/master/Dmf/Modules.Library/Dmf_CrashDump.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_kbugcheck_add_pages">KBUGCHECK_ADD_PAGES</a>

<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kbugcheck_callback_reason">KBUGCHECK_CALLBACK_REASON</a>

<a href="/windows-hardware/drivers/kernel/eprocess">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a>

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterbugcheckreasoncallback">KeDeregisterBugCheckReasonCallback</a>

<a href="/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.