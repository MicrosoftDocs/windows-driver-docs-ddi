---
UID: NF:ntifs.RtlGenerate8dot3Name
title: RtlGenerate8dot3Name function (ntifs.h)
description: The RtlGenerate8dot3Name routine generates a short (8.3) name for the specified long file name.
old-location: ifsk\rtlgenerate8dot3name.htm
tech.root: ifsk
ms.assetid: 7e8f84c4-c251-4f80-a8fc-465e44c14405
ms.date: 04/16/2018
keywords: ["RtlGenerate8dot3Name function"]
ms.keywords: RtlGenerate8dot3Name, RtlGenerate8dot3Name routine [Installable File System Drivers], ifsk.rtlgenerate8dot3name, ntifs/RtlGenerate8dot3Name, rtlref_e28a5c45-d430-43a7-89f8-4f193971715c.xml
f1_keywords:
 - "ntifs/RtlGenerate8dot3Name"
 - "RtlGenerate8dot3Name"
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlGenerate8dot3Name
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlGenerate8dot3Name function


## -description


The <b>RtlGenerate8dot3Name</b> routine generates a short (8.3) name for the specified long file name. 


## -parameters




### -param Name [in]

Pointer to a Unicode string containing the long name for the file. Any leading periods in this file name are skipped during generation of a corresponding short name. 


### -param AllowExtendedCharacters [in]

Set to <b>TRUE</b> if the generated short file name can contain extended characters. Set to <b>FALSE</b> if the generated short file name must contain only characters within the current code page's ANSI or OEM range from 0x20 (space) through 0x7f (DEL). 


### -param Context [in, out]

Pointer to a caller-allocated buffer for use by <b>RtlGenerate8dot3Name</b>. Before calling <b>RtlGenerate8dot3Name</b> for the first time to translate the given long file name, the caller is responsible for filling the buffer with zeros.


### -param Name8dot3 [in, out]

Pointer to a caller-allocated buffer to receive the generated short file name. The size of this buffer must be at least 24 bytes (12 Unicode characters). 


## -returns



This routine returns STATUS_SUCCESS if a short name is successfully generated. It returns STATUS_FILE_SYSTEM_LIMITATION if the system can not generate a unique short name for a given file. It returns this error after 1 million retry attempts for a single given long name.




## -remarks



<b>RtlGenerate8dot3Name</b> returns a generated short name with at most eight characters, followed immediately by a period and up to three more characters. 

<b>RtlGenerate8dot3Name</b> can be called repeatedly. For example, if the initially generated short name is a duplicate of an existing file name, the caller can pass the same parameters to <b>RtlGenerate8dot3Name</b> again. In this case, the buffer at <i>Context</i> should not be reinitialized with zeros. This buffer should be zeroed only for the initial call to translate a given long name. On repeated calls for the same long name, <b>RtlGenerate8dot3Name</b> stores private context information in this buffer to prevent name collisions. 

Two calls to <b>RtlGenerate8dot3Name</b> with the same <i>Name</i> and <i>Context</i> are not guaranteed to return the same result. Callers should assume that the mapping of long name to short name is nondeterministic. 

<b>RtlGenerate8dot3Name</b> translates the given long name using the current system code page, discarding any invalid or superfluous characters in the input long name. When <i>AllowExtendedCharacters</i> is set to <b>TRUE</b>, ANSI or double-byte character set (DBCS) characters that map to uppercase OEM characters can become part of a returned short name. 

<b>RtlGenerate8dot3Name</b> returns a short file name with uppercase alphabetic characters. It returns underscores in the generated short name for any of the following characters that it encounters in the given long name:

<ul>
<li>
Colons and semicolons 

</li>
<li>
Commas 

</li>
<li>
Plus and equal signs 

</li>
<li>
Square brackets 

</li>
</ul>
For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlisnamelegaldos8dot3">RtlIsNameLegalDOS8Dot3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlisvalidoemcharacter">RtlIsValidOemCharacter</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

