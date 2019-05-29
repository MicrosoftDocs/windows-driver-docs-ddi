---
UID: NF:ntifs.RtlIsNameLegalDOS8Dot3
title: RtlIsNameLegalDOS8Dot3 function (ntifs.h)
description: The RtlIsNameLegalDOS8Dot3 routine determines whether a given name represents a valid short (8.3) file name.
old-location: ifsk\rtlisnamelegaldos8dot3.htm
tech.root: ifsk
ms.assetid: 27aa6bd1-c4e2-427e-a9e4-383d66fe2d61
ms.date: 04/16/2018
ms.keywords: RtlIsNameLegalDOS8Dot3, RtlIsNameLegalDOS8Dot3 routine [Installable File System Drivers], ifsk.rtlisnamelegaldos8dot3, ntifs/RtlIsNameLegalDOS8Dot3, rtlref_73bcf962-f0aa-4fa1-9e45-0a471a6b2c40.xml
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlIsNameLegalDOS8Dot3
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsNameLegalDOS8Dot3 function


## -description


The <b>RtlIsNameLegalDOS8Dot3</b> routine determines whether a given name represents a valid short (8.3) file name. 


## -parameters




### -param Name [in]

Pointer to a Unicode string containing the file name. 


### -param OemName [in, out]

Pointer to an optional caller-allocated buffer that receives a counted OEM string corresponding to the Unicode string at <i>Name</i>. 


### -param NameContainsSpaces [out, optional]

Pointer to an optional BOOLEAN value that receives <b>TRUE</b> if the string at <i>Name</i> contains embedded spaces, <b>FALSE</b> otherwise. This value is valid only if <b>RtlIsNameLegalDOS8Dot3</b> returns <b>TRUE</b>. 


## -returns



<b>RtlIsNameLegalDOS8Dot3</b> returns <b>TRUE</b> if the string at <i>Name</i> is a legal short (8.3) file name, <b>FALSE</b> otherwise.




## -remarks



<b>RtlIsNameLegalDOS8Dot3</b> translates the Unicode string at <i>Name</i> using the OEM code page that was installed as the current system code page at system boot time, and converts the translated string to uppercase. (If the caller supplied a buffer at <i>OemName</i>, this buffer receives the resulting string.) <b>RtlIsNameLegalDOS8Dot3</b> checks that the name is a properly formatted 8.3 name and contains only legal characters.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 

If the block of memory at <i>Name</i> is nonpaged, the caller can be running at IRQL &lt;= DISPATCH_LEVEL. Otherwise, callers of <b>RtlIsNameLegalDOS8Dot3</b> must be running at IRQL &lt; DISPATCH_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552285">RtlGenerate8dot3Name</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

