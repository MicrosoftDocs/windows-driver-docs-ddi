---
UID: NF:ntifs.RtlRemoveUnicodePrefix
title: RtlRemoveUnicodePrefix function
author: windows-driver-content
description: The RtlRemoveUnicodePrefix routine removes an element from a prefix table.
old-location: ifsk\rtlremoveunicodeprefix.htm
old-project: ifsk
ms.assetid: b2f996b1-0c1a-4ad5-a4c4-5d84ca94c5a1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlRemoveUnicodePrefix, ntifs/RtlRemoveUnicodePrefix, rtlref_a6eb361a-f00b-4377-913c-8494c49d4064.xml, RtlRemoveUnicodePrefix routine [Installable File System Drivers], ifsk.rtlremoveunicodeprefix
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
-	RtlRemoveUnicodePrefix
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlRemoveUnicodePrefix function


## -description


The <b>RtlRemoveUnicodePrefix</b> routine removes an element from a prefix table. 


## -syntax


````
VOID RtlRemoveUnicodePrefix(
  _In_ PUNICODE_PREFIX_TABLE       PrefixTable,
  _In_ PUNICODE_PREFIX_TABLE_ENTRY PrefixTableEntry
);
````


## -parameters




### -param PrefixTable [in]

Pointer to the prefix table. The table must have been initialized by calling <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>.


### -param PrefixTableEntry [in]

Pointer to the prefix table element to be deleted. 


## -returns


None



## -remarks


File systems must call <a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtlinsertunicodeprefix.md">RtlInsertUnicodePrefix</a>

<a href="..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md">RtlInitializeUnicodePrefix</a>

<a href="..\ntifs\nf-ntifs-rtlfindunicodeprefix.md">RtlFindUnicodePrefix</a>

<a href="..\ntifs\nf-ntifs-rtlnextunicodeprefix.md">RtlNextUnicodePrefix</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlRemoveUnicodePrefix routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

