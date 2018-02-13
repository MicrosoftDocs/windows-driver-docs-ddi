---
UID: NF:ntifs.RtlNextUnicodePrefix
title: RtlNextUnicodePrefix function
author: windows-driver-content
description: The RtlNextUnicodePrefix routine is used to enumerate the elements in a Unicode prefix table.
old-location: ifsk\rtlnextunicodeprefix.htm
old-project: ifsk
ms.assetid: c4f43f4c-a598-4bda-9325-21440f56ab17
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RtlNextUnicodePrefix routine [Installable File System Drivers], rtlref_75c728f8-96b0-4e46-b47a-7d30ac61872c.xml, ifsk.rtlnextunicodeprefix, ntifs/RtlNextUnicodePrefix, RtlNextUnicodePrefix
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlNextUnicodePrefix
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlNextUnicodePrefix function


## -description


The <b>RtlNextUnicodePrefix</b> routine is used to enumerate the elements in a Unicode prefix table. 


## -syntax


````
PUNICODE_PREFIX_TABLE_ENTRY RtlNextUnicodePrefix(
  _In_ PUNICODE_PREFIX_TABLE PrefixTable,
  _In_ BOOLEAN               Restart
);
````


## -parameters




### -param PrefixTable [in]

Pointer to the prefix table. The table must have been initialized by calling <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>.


### -param Restart [in]

Set to <b>TRUE</b> if the enumeration is to start at the first element in the table. Set to <b>FALSE</b> if resuming the enumeration from a previous call.

To enumerate all elements in the table, use <b>RtlNextUnicodePrefix</b> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>for (p = RtlNextUnicodePrefix ( Table, TRUE );
     p != NULL;
     p = RtlNextUnicodePrefix ( Table, FALSE )) {
        // Process the element pointed to by p
}</pre>
</td>
</tr>
</table></span></div>

## -returns



<b>RtlNextUnicodePrefix</b> returns a pointer to the next element, if one exists. If there are no more elements in the table, <b>RtlNextUnicodePrefix</b> returns <b>NULL</b>. 




## -remarks



File systems must call <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlinsertunicodeprefix.md">RtlInsertUnicodePrefix</a>



<a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>



<a href="..\ntifs\nf-ntifs-rtlfindunicodeprefix.md">RtlFindUnicodePrefix</a>



<a href="..\ntifs\nf-ntifs-rtlremoveunicodeprefix.md">RtlRemoveUnicodePrefix</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlNextUnicodePrefix routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

