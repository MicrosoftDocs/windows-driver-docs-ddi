---
UID: NF:ntifs.RtlFindUnicodePrefix
title: RtlFindUnicodePrefix function (ntifs.h)
description: The RtlFindUnicodePrefix routine searches for the best match for a given Unicode file name in a prefix table.
old-location: ifsk\rtlfindunicodeprefix.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlFindUnicodePrefix function"]
ms.keywords: RtlFindUnicodePrefix, RtlFindUnicodePrefix routine [Installable File System Drivers], ifsk.rtlfindunicodeprefix, ntifs/RtlFindUnicodePrefix, rtlref_55dbfa12-5de6-44e0-8488-6e83abfaad84.xml
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFindUnicodePrefix
 - ntifs/RtlFindUnicodePrefix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFindUnicodePrefix
---

# RtlFindUnicodePrefix function


## -description

The <b>RtlFindUnicodePrefix</b> routine searches for the best match for a given Unicode file name in a prefix table.

## -parameters

### -param PrefixTable 

[in]
Pointer to the prefix table. The table must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a>.

### -param FullName 

[in]
Pointer to a Unicode string containing the full pathname for a file.

### -param CaseInsensitiveIndex 

[in]
Position in the file name and prefix strings at which the comparison is to become case-insensitive. The string comparison is case-sensitive for the first <i>CaseInsensitiveIndex</i> characters in each string, case-insensitive for the remainder of the string.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
String comparison is case-insensitive.

</td>
</tr>
<tr>
<td>
1..<i>FullName.Length</i>-1

</td>
<td>
String comparison is case-sensitive for characters at positions 0 through <i>CaseInsensitiveIndex</i>-1, case-insensitive for characters from position <i>CaseInsensitiveIndex</i> to the end of the string.

</td>
</tr>
<tr>
<td>
<i>FullName.Length</i>

</td>
<td>
String comparison is case-sensitive.

</td>
</tr>
</table>

## -returns

<b>RtlFindUnicodePrefix</b> returns a pointer to the longest proper prefix found for the given string at <i>FullName</i>. If no matching prefix is found, <b>RtlFindUnicodePrefix</b> returns <b>NULL</b>.

## -remarks

Each prefix entry in the table is a pathname relative to the root directory of a file system volume. To be well-formed, the prefix must begin with a single backslash (\). 

When it finds a matching prefix, <b>RtlFindUnicodePrefix</b> rebalances the prefix table's splay tree.

File systems must call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines">Run-Time Library (RTL) Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializeunicodeprefix">RtlInitializeUnicodePrefix</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinsertunicodeprefix">RtlInsertUnicodePrefix</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlnextunicodeprefix">RtlNextUnicodePrefix</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlremoveunicodeprefix">RtlRemoveUnicodePrefix</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
