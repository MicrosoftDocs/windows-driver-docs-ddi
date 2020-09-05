---
UID: NF:ntifs.RtlNextUnicodePrefix
title: RtlNextUnicodePrefix function (ntifs.h)
description: The RtlNextUnicodePrefix routine is used to enumerate the elements in a Unicode prefix table.
old-location: ifsk\rtlnextunicodeprefix.htm
tech.root: ifsk
ms.assetid: c4f43f4c-a598-4bda-9325-21440f56ab17
ms.date: 04/16/2018
keywords: ["RtlNextUnicodePrefix function"]
ms.keywords: RtlNextUnicodePrefix, RtlNextUnicodePrefix routine [Installable File System Drivers], ifsk.rtlnextunicodeprefix, ntifs/RtlNextUnicodePrefix, rtlref_75c728f8-96b0-4e46-b47a-7d30ac61872c.xml
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
 - RtlNextUnicodePrefix
 - ntifs/RtlNextUnicodePrefix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNextUnicodePrefix
---

# RtlNextUnicodePrefix function


## -description

The <b>RtlNextUnicodePrefix</b> routine is used to enumerate the elements in a Unicode prefix table.

## -parameters

### -param PrefixTable 

[in]
Pointer to the prefix table. The table must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a>.

### -param Restart 

[in]
Set to <b>TRUE</b> if the enumeration is to start at the first element in the table. Set to <b>FALSE</b> if resuming the enumeration from a previous call.

To enumerate all elements in the table, use <b>RtlNextUnicodePrefix</b> as follows:


```
for (p = RtlNextUnicodePrefix ( Table, TRUE );
     p != NULL;
     p = RtlNextUnicodePrefix ( Table, FALSE )) {
        // Process the element pointed to by p
}
```


## -returns

<b>RtlNextUnicodePrefix</b> returns a pointer to the next element, if one exists. If there are no more elements in the table, <b>RtlNextUnicodePrefix</b> returns <b>NULL</b>.

## -remarks

File systems must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfindunicodeprefix">RtlFindUnicodePrefix</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinsertunicodeprefix">RtlInsertUnicodePrefix</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlremoveunicodeprefix">RtlRemoveUnicodePrefix</a>

