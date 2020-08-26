---
UID: NF:ntddk.IoIsValidIrpStatus
title: IoIsValidIrpStatus function (ntddk.h)
description: The IoIsValidIrpStatus routine validates the specified NTSTATUS status code value.
old-location: kernel\ioisvalidirpstatus.htm
tech.root: kernel
ms.assetid: 0A995357-A578-41C6-A1B8-ABD251C16C83
ms.date: 04/30/2018
keywords: ["IoIsValidIrpStatus function"]
ms.keywords: IoIsValidIrpStatus, IoIsValidIrpStatus routine [Kernel-Mode Driver Architecture], kernel.ioisvalidirpstatus, ntddk/IoIsValidIrpStatus
f1_keywords:
 - "ntddk/IoIsValidIrpStatus"
 - "IoIsValidIrpStatus"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any level.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoIsValidIrpStatus
targetos: Windows
req.typenames: 
---

# IoIsValidIrpStatus function


## -description


The <b>IoIsValidIrpStatus</b> routine validates the specified NTSTATUS status code value.


## -parameters




### -param Status 
[in]
The status code to be validated.


## -returns



<b>IoIsValidIrpStatus</b> returns <b>TRUE</b> if the <i>Status</i> parameter is a well-formed NTSTATUS value. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



Driver developers can define custom NTSTATUS values for use as status codes for <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> requests. Drivers can call <b>IoIsValidIrpStatus</b> to validate the status codes for these requests. This routine is useful for detecting an uninitialized or corrupted <b>Status</b> value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-status-blocks">I/O status block</a> of an IRP.

<b>IoIsValidIrpStatus</b> detects invalid status codes that obviously violate the rules for defining custom NTSTATUS values, but might not detect invalid status codes that appear to follow the rules. The routine might return <b>TRUE</b> for a <i>Status</i> parameter that is not a valid NTSTATUS code value, but rarely, if ever, returns <b>FALSE</b> for a valid NTSTATUS code.

<b>IoIsValidIrpStatus</b> examines the <b>Sev</b>, <b>Facility</b>, and <b>Code</b> fields in the <i>Status</i> parameter value to determine whether the combination of values in these fields conforms to the published guidelines. If the <b>C</b> bit of the <i>Status</i> parameter is set, <b>IoIsValidIrpStatus</b> returns <b>TRUE</b> regardless of the other field values in <i>Status</i>.

For more information about these fields, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/defining-new-ntstatus-values">Defining New NTSTATUS Values</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>
 

 

