---
UID: NF:ntifs.RtlCreateUnicodeString
title: RtlCreateUnicodeString function
author: windows-driver-content
description: The RtlCreateUnicodeString routine creates a new counted Unicode string.
old-location: ifsk\rtlcreateunicodestring.htm
old-project: ifsk
ms.assetid: f101fc66-40a9-4077-b651-cef0a0e247d4
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RtlCreateUnicodeString routine [Installable File System Drivers], rtlref_8d7cd5ce-a1c9-48a0-86a9-86120954d328.xml, ntifs/RtlCreateUnicodeString, RtlCreateUnicodeString, ifsk.rtlcreateunicodestring
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlCreateUnicodeString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlCreateUnicodeString function


## -description


The <b>RtlCreateUnicodeString</b> routine creates a new counted Unicode string.


## -syntax


````
BOOLEAN RtlCreateUnicodeString(
  _Out_ PUNICODE_STRING DestinationString,
  _In_  PCWSTR          SourceString
);
````


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

<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateUnicodeString routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

