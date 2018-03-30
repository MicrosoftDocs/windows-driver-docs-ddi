---
UID: NF:ntifs.RtlOemStringToUnicodeString
title: RtlOemStringToUnicodeString function
author: windows-driver-content
description: The RtlOemStringToUnicodeString routine translates a given source string into a null-terminated Unicode string using the current system OEM code page.
old-location: ifsk\rtloemstringtounicodestring.htm
old-project: ifsk
ms.assetid: 0420718f-3d0f-4f15-85ec-c2cdfa930023
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlOemStringToUnicodeString, RtlOemStringToUnicodeString routine [Installable File System Drivers], ifsk.rtloemstringtounicodestring, ntifs/RtlOemStringToUnicodeString, rtlref_6b1f3210-6b02-4f20-9887-b7efd0090b7f.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlOemStringToUnicodeString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlOemStringToUnicodeString function


## -description


The <b>RtlOemStringToUnicodeString</b> routine translates a given source string into a null-terminated Unicode string using the current system OEM code page. 


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the translated string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the null-terminated Unicode string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlOemStringToUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the OEM string to be translated to Unicode. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlOemStringToUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>. 


## -returns



<b>RtlOemStringToUnicodeString</b> returns STATUS_SUCCESS if it returns a translated string at <i>DestinationString</i>. Otherwise, no storage was allocated and no conversion was done. 




## -remarks



<b>RtlOemStringToUnicodeString</b> translates the given source string using the OEM code page that was installed as the current system code page at system boot time. 

This routine does not modify the source string. It returns a NULL-terminated Unicode string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553142">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553147">RtlOemStringToUnicodeSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553157">RtlOemToUnicodeN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553255">RtlUnicodeStringToOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

