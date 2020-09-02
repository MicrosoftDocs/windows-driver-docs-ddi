---
UID: NF:ntifs.FsRtlLogCcFlushError
title: FsRtlLogCcFlushError function (ntifs.h)
description: The FsRtlLogCcFlushError routine logs a lost delayed-write error and displays a dialog box to the user.
old-location: ifsk\fsrtllogccflusherror.htm
tech.root: ifsk
ms.assetid: e516758d-d1fe-4977-93bb-f427972fdd3c
ms.date: 04/16/2018
keywords: ["FsRtlLogCcFlushError function"]
ms.keywords: FsRtlLogCcFlushError, FsRtlLogCcFlushError routine [Installable File System Drivers], fsrtlref_5e72d84c-d788-4b6d-b5fe-3e9b06b0e074.xml, ifsk.fsrtllogccflusherror, ntifs/FsRtlLogCcFlushError
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlLogCcFlushError
 - ntifs/FsRtlLogCcFlushError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlLogCcFlushError
---

# FsRtlLogCcFlushError function


## -description

The <b>FsRtlLogCcFlushError</b> routine logs a lost delayed-write error and displays a dialog box to the user.

## -parameters

### -param FileName 

[in]
The name of the file that could not be flushed.

### -param DeviceObject 

[in]
A pointer to the device object that this log entry should be filed against.

### -param SectionObjectPointer 

[in]
A pointer to the section object for the file on which the flush failed.

### -param FlushError 

[in]
The error returned by the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>.

### -param Flags 

[in]
A value of 0 or a bitwise combination of one or more of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FSRTL_CC_FLUSH_ERROR_FLAG_NO_HARD_ERROR

</td>
<td>
Suppresses presentation of an informational dialog box to the user.

</td>
</tr>
<tr>
<td>
FSRTL_CC_FLUSH_ERROR_FLAG_NO_LOG_ENTRY

</td>
<td>
Suppresses generation of a system error log entry.

</td>
</tr>
</table>

## -returns

The <b>FsRtlLogCcFlushError</b> routine returns STATUS_SUCCESS on success or another NTSTATUS value, such as STATUS_INSUFFICIENT_RESOURCES.

## -remarks

Unless the call includes appropriate <i>Flags</i>, the <b>FsRtlLogCcFlushError</b> routine uses <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioraiseinformationalharderror">IoRaiseInformationalHardError</a> to display a dialog box to the user, including the specific error and <i>FileName</i>, and uses <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a> logs the error. 

If the entire <i>FileName</i> cannot fit within the log buffer, the routine inserts an ellipsis into the file name.

If the cache still has pages that have been modified, the error is not fatal. The routine returns to the caller without logging an error or displaying the dialog box. 

If the error is fatal, the routine increments the lost delayed write counter in the processor control block (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PRCB</a>). This counter can be used in troubleshooting lost delayed write errors.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioraiseinformationalharderror">IoRaiseInformationalHardError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>

