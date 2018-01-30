---
UID: NF:ntifs.RtlIsNameLegalDOS8Dot3
title: RtlIsNameLegalDOS8Dot3 function
author: windows-driver-content
description: The RtlIsNameLegalDOS8Dot3 routine determines whether a given name represents a valid short (8.3) file name.
old-location: ifsk\rtlisnamelegaldos8dot3.htm
old-project: ifsk
ms.assetid: 27aa6bd1-c4e2-427e-a9e4-383d66fe2d61
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: rtlref_73bcf962-f0aa-4fa1-9e45-0a471a6b2c40.xml, ntifs/RtlIsNameLegalDOS8Dot3, ifsk.rtlisnamelegaldos8dot3, RtlIsNameLegalDOS8Dot3, RtlIsNameLegalDOS8Dot3 routine [Installable File System Drivers]
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlIsNameLegalDOS8Dot3
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlIsNameLegalDOS8Dot3 function


## -description


The <b>RtlIsNameLegalDOS8Dot3</b> routine determines whether a given name represents a valid short (8.3) file name. 


## -syntax


````
BOOLEAN RtlIsNameLegalDOS8Dot3(
  _In_      PCUNICODE_STRING Name,
  _Inout_   POEM_STRING      OemName,
  _Out_opt_ PBOOLEAN         NameContainsSpaces
);
````


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

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>

<a href="..\ntifs\nf-ntifs-rtlgenerate8dot3name.md">RtlGenerate8dot3Name</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsNameLegalDOS8Dot3 routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

