---
UID: NF:ntifs.RtlRemoveUnicodePrefix
title: RtlRemoveUnicodePrefix function (ntifs.h)
description: The RtlRemoveUnicodePrefix routine removes an element from a prefix table.
old-location: ifsk\rtlremoveunicodeprefix.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlRemoveUnicodePrefix function"]
ms.keywords: RtlRemoveUnicodePrefix, RtlRemoveUnicodePrefix routine [Installable File System Drivers], ifsk.rtlremoveunicodeprefix, ntifs/RtlRemoveUnicodePrefix, rtlref_a6eb361a-f00b-4377-913c-8494c49d4064.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlRemoveUnicodePrefix
 - ntifs/RtlRemoveUnicodePrefix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlRemoveUnicodePrefix
---

# RtlRemoveUnicodePrefix function


## -description

The <b>RtlRemoveUnicodePrefix</b> routine removes an element from a prefix table.

## -parameters

### -param PrefixTable 

[in]
Pointer to the prefix table. The table must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a>.

### -param PrefixTableEntry 

[in]
Pointer to the prefix table element to be deleted.

## -returns

None

## -remarks

File systems must call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/index">Strings</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfindunicodeprefix">RtlFindUnicodePrefix</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinsertunicodeprefix">RtlInsertUnicodePrefix</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlnextunicodeprefix">RtlNextUnicodePrefix</a>
