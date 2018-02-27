---
UID: NF:ntifs.RtlDowncaseUnicodeString
title: RtlDowncaseUnicodeString function
author: windows-driver-content
description: The RtlDowncaseUnicodeString routine converts the specified Unicode source string to lowercase. The translation conforms to the current system locale information.
old-location: ifsk\rtldowncaseunicodestring.htm
old-project: ifsk
ms.assetid: c611b051-45fe-4509-bf2c-7059d578ea05
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlDowncaseUnicodeString, RtlDowncaseUnicodeString routine [Installable File System Drivers], ifsk.rtldowncaseunicodestring, ntifs/RtlDowncaseUnicodeString, rtlref_140e7faa-096a-49df-a2b7-87776cfc5b38.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
-	RtlDowncaseUnicodeString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlDowncaseUnicodeString function


## -description


The <b>RtlDowncaseUnicodeString</b> routine converts the specified Unicode source string to lowercase. The translation conforms to the current system locale information.


## -syntax


````
NTSTATUS RtlDowncaseUnicodeString(
       PUNICODE_STRING  DestinationString,
  _In_ PCUNICODE_STRING SourceString,
  _In_ BOOLEAN          AllocateDestinationString
);
````


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the converted Unicode string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the Unicode data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlDowncaseUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the source Unicode string to be converted to lowercase. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlDowncaseUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>. 


## -returns



If the operation succeeds, <b>RtlDowncaseUnicodeString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated and no conversion was done. 




## -remarks



If caller sets <i>AllocateDestinationString</i> to <b>TRUE</b>, <b>RtlDowncaseUnicodeString</b> replaces the <b>Buffer</b> member of <i>DestinationString</i> with a pointer to the buffer it allocates. The old value can be overwritten even when the routine returns an error status code.

<b>RtlDowncaseUnicodeString</b> does not modify the source string.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\wudfwdm\nf-wudfwdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>



<a href="..\ntddk\nf-ntddk-rtlupcaseunicodestring.md">RtlUpcaseUnicodeString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDowncaseUnicodeString routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

