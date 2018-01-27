---
UID: NF:ntifs.RtlFindUnicodePrefix
title: RtlFindUnicodePrefix function
author: windows-driver-content
description: The RtlFindUnicodePrefix routine searches for the best match for a given Unicode file name in a prefix table.
old-location: ifsk\rtlfindunicodeprefix.htm
old-project: ifsk
ms.assetid: 525db78d-b25c-4325-ac71-b992564a19c0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlFindUnicodePrefix routine [Installable File System Drivers], ntifs/RtlFindUnicodePrefix, ifsk.rtlfindunicodeprefix, rtlref_55dbfa12-5de6-44e0-8488-6e83abfaad84.xml, RtlFindUnicodePrefix
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	RtlFindUnicodePrefix
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlFindUnicodePrefix function


## -description


The <b>RtlFindUnicodePrefix</b> routine searches for the best match for a given Unicode file name in a prefix table. 


## -syntax


````
PUNICODE_PREFIX_TABLE_ENTRY RtlFindUnicodePrefix(
  _In_ PUNICODE_PREFIX_TABLE PrefixTable,
  _In_ PCUNICODE_STRING      FullName,
  _In_ ULONG                 CaseInsensitiveIndex
);
````


## -parameters




### -param PrefixTable [in]

Pointer to the prefix table. The table must have been initialized by calling <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>.


### -param FullName [in]

Pointer to a Unicode string containing the full pathname for a file. 


### -param CaseInsensitiveIndex [in]

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

File systems must call <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtlremoveunicodeprefix.md">RtlRemoveUnicodePrefix</a>

<a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntifs\nf-ntifs-rtlnextunicodeprefix.md">RtlNextUnicodePrefix</a>

<a href="..\ntifs\nf-ntifs-rtlinsertunicodeprefix.md">RtlInsertUnicodePrefix</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlFindUnicodePrefix routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

