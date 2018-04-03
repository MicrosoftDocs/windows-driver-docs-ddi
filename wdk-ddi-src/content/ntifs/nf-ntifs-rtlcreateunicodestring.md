---
UID: NF:ntifs.RtlCreateUnicodeString
title: RtlCreateUnicodeString function
author: windows-driver-content
description: The RtlCreateUnicodeString routine creates a new counted Unicode string.
old-location: ifsk\rtlcreateunicodestring.htm
old-project: ifsk
ms.assetid: f101fc66-40a9-4077-b651-cef0a0e247d4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlCreateUnicodeString, RtlCreateUnicodeString routine [Installable File System Drivers], ifsk.rtlcreateunicodestring, ntifs/RtlCreateUnicodeString, rtlref_8d7cd5ce-a1c9-48a0-86a9-86120954d328.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlCreateUnicodeString
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlCreateUnicodeString function


## -description


The <b>RtlCreateUnicodeString</b> routine creates a new counted Unicode string.


## -parameters




### -param DestinationString [out]

Pointer to the newly allocated and initialized Unicode string. 


### -param SourceString [in]

Pointer to a null-terminated Unicode string with which to initialize the new string.


## -returns



<b>RtlCreateUnicodeString</b> returns <b>TRUE</b> if the Unicode string was successfully created, <b>FALSE</b> otherwise.




## -remarks



The <i>DestinationString</i> is allocated from paged pool. The caller is responsible for freeing the <i>DestinationString</i> by calling <b>RtlFreeUnicodeString</b>.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

