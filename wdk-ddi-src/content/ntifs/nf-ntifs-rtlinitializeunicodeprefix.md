---
UID: NF:ntifs.RtlInitializeUnicodePrefix
title: RtlInitializeUnicodePrefix function
author: windows-driver-content
description: The RtlInitializeUnicodePrefix routine initializes a prefix table.
old-location: ifsk\rtlinitializeunicodeprefix.htm
tech.root: ifsk
ms.assetid: 8891641a-392c-4c2b-aa5a-9464774d8610
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlInitializeUnicodePrefix, RtlInitializeUnicodePrefix routine [Installable File System Drivers], ifsk.rtlinitializeunicodeprefix, ntifs/RtlInitializeUnicodePrefix, rtlref_cc6170fe-7f41-45ac-909c-75e341ad8d9c.xml
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
-	RtlInitializeUnicodePrefix
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInitializeUnicodePrefix function


## -description


The <b>RtlInitializeUnicodePrefix</b> routine initializes a prefix table.


## -parameters




### -param PrefixTable [out]

Pointer to caller-allocated buffer, which must be at least <b>sizeof</b>(UNICODE_PREFIX_TABLE), for the prefix table header. <b>RtlInitializeUnicodePrefix</b> initializes this header, which should be considered opaque by the caller. 


## -returns



None




## -remarks



File systems must call <b>RtlInitializeUnicodePrefix</b> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545293">ExInitializeFastMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552272">RtlFindUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553038">RtlInsertUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553123">RtlNextUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553193">RtlRemoveUnicodePrefix</a>
 

 

