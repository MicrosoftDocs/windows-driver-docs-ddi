---
UID: NF:ntddk.KeGetCurrentProcessorNumberEx
title: KeGetCurrentProcessorNumberEx function (ntddk.h)
description: The KeGetCurrentProcessorNumberEx routine gets the processor number of the logical processor that the caller is running on.
old-location: kernel\kegetcurrentprocessornumberex.htm
tech.root: kernel
ms.assetid: eb66a17e-2e85-453c-8b39-091f0dc8c29b
ms.date: 04/30/2018
keywords: ["KeGetCurrentProcessorNumberEx function"]
ms.keywords: KeGetCurrentProcessorNumberEx, KeGetCurrentProcessorNumberEx routine [Kernel-Mode Driver Architecture], k105_3eea6705-7267-452a-88c2-1597c6f19828.xml, kernel.kegetcurrentprocessornumberex, wdm/KeGetCurrentProcessorNumberEx
req.header: ntddk.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeGetCurrentProcessorNumberEx
 - ntddk/KeGetCurrentProcessorNumberEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeGetCurrentProcessorNumberEx
---

# KeGetCurrentProcessorNumberEx function (ntddk.h)


## -description

The <b>KeGetCurrentProcessorNumberEx</b> routine gets the processor number of the logical processor that the caller is running on.

## -parameters

### -param ProcNumber 

[out, optional]
A pointer to a caller-allocated buffer into which the routine writes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a> structure that identifies the current logical processor. This structure contains the group number and the group-relative processor number. You can set this parameter to <b>NULL</b> if you do not need this information.

## -returns

<b>KeGetCurrentProcessorNumberEx</b> returns the systemwide processor index of the logical processor that the caller is running on.

## -remarks

If <i>ProcNumber</i> is non-<b>NULL</b>, the buffer that is pointed to by <i>ProcNumber</i> must be large enough to contain a PROCESSOR_NUMBER structure. In contrast to this structure, which contains a group number and a group-relative processor number, the return value is a processor index that identifies the processor across the entire multiprocessor system.

For example, if a multiprocessor system contains two groups, and each group contains 64 logical processors, the processor numbers in each group range from 0 to 63, but the systemwide processor indexes range from 0 to 127.

A related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kegetcurrentprocessornumber">KeGetCurrentProcessorNumber</a>, returns the current processor number, but this routine, unlike <b>KeGetCurrentProcessorNumberEx</b>, does not provide a group number for the processor. In Windows 7 and later versions of the Windows operating system, <b>KeGetCurrentProcessorNumber</b> returns the group-relative processor number if the caller is running on a processor in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. However, if the caller is running on a processor in any group other than group 0, this routine returns a number that is less than the number of processors in group 0. This behavior ensures that the return value is less than the return value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryactiveprocessorcount">KeQueryActiveProcessorCount</a> routine. Existing drivers that call <b>KeGetCurrentProcessorNumber</b> and that use no group-oriented features run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeGetCurrentProcessorNumberEx</b> instead of <b>KeGetCurrentProcessorNumber</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kegetcurrentprocessornumber">KeGetCurrentProcessorNumber</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryactiveprocessorcount">KeQueryActiveProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a>

