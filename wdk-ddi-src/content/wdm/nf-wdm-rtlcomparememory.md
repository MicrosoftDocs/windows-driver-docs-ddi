---
UID: NF:wdm.RtlCompareMemory
title: RtlCompareMemory function (wdm.h)
description: The RtlCompareMemory routine compares two blocks of memory and returns the number of bytes that match until the first difference.
tech.root: kernel
ms.date: 04/06/2022
keywords: ["RtlCompareMemory function"]
ms.keywords: RtlCompareMemory, RtlCompareMemory routine [Kernel-Mode Driver Architecture], k109_3deee1b7-0b3a-4d24-8c0f-5e428d051a02.xml, kernel.rtlcomparememory, wdm/RtlCompareMemory
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib; OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); Kernel32.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCompareMemory
 - wdm/RtlCompareMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - Kernel32.dll
 - NtosKrnl.exe
 - API-MS-Win-Core-rtlsupport-l1-1-0.dll
 - API-MS-Win-Core-rtlsupport-l1-2-0.dll
api_name:
 - RtlCompareMemory
---

# RtlCompareMemory function

## -description

The **RtlCompareMemory** routine compares two blocks of memory and returns the number of bytes that match until the first difference.

## -parameters

### -param Source1 [in]

A pointer to the first block of memory.

### -param Source2 [in]

A pointer to the second block of memory.

### -param Length [in]

The number of bytes to compare.

## -returns

**RtlCompareMemory** returns the number of bytes in the two blocks that match. If all bytes match up to the specified *Length* value, the *Length* value is returned.

## -remarks

The routine starts by comparing the first byte in the first block to the first byte in the second block, and continues to compare successive bytes in the two blocks while the bytes match. The routine stops comparing bytes when it encounters the first pair of bytes that are not equal, or when the number of matching bytes equals the *Length* parameter value, whichever occurs first.

Callers of **RtlCompareMemory** can be running at any IRQL if both blocks of memory are resident.
