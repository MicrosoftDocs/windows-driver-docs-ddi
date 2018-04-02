---
UID: NF:ntifs.RtlInsertUnicodePrefix
title: RtlInsertUnicodePrefix function
author: windows-driver-content
description: The RtlInsertUnicodePrefix routine inserts a new element into a Unicode prefix table.
old-location: ifsk\rtlinsertunicodeprefix.htm
old-project: ifsk
ms.assetid: d8a2fa19-8f44-4088-b515-69c9f2119714
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlInsertUnicodePrefix, RtlInsertUnicodePrefix routine [Installable File System Drivers], ifsk.rtlinsertunicodeprefix, ntifs/RtlInsertUnicodePrefix, rtlref_5c8e1a42-5c73-4029-9c1f-5426e43e123c.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlInsertUnicodePrefix
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlInsertUnicodePrefix function


## -description


The <b>RtlInsertUnicodePrefix</b> routine inserts a new element into a Unicode prefix table. 


## -parameters




### -param PrefixTable [in]

Pointer to the prefix table. The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553015">RtlInitializeUnicodePrefix</a>.


### -param Prefix [in]

Pointer to the name string to be inserted with the element at <i>PrefixTableEntry</i>. 


### -param PrefixTableEntry [out]

Pointer to caller-allocated storage, which must be at least <b>sizeof</b>(UNICODE_PREFIX_TABLE_ENTRY), for the element to be inserted for the new prefix. <b>RtlInsertUnicodePrefix</b> initializes this element, which should be considered opaque by the caller. 


## -returns



<b>RtlInsertUnicodePrefix</b> returns <b>TRUE</b> if the new element was inserted in the prefix table, or it returns <b>FALSE</b> if a duplicate element already exists in the prefix table. 




## -remarks



Each prefix entry in the table is a pathname relative to the root directory of a file system volume. To be well-formed, the prefix must begin with a single backslash (\). 

After inserting the new element, <b>RtlInsertUnicodePrefix</b> rebalances the prefix table's splay tree.

File systems must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553015">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552272">RtlFindUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553015">RtlInitializeUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553123">RtlNextUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553193">RtlRemoveUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

