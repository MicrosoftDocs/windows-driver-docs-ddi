---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlIsHpfsDbcsLegal~r3
title: FsRtlIsHpfsDbcsLegal function
author: windows-driver-content
description: The FsRtlIsHpfsDbcsLegal routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal HPFS file name.
old-location: ifsk\fsrtlishpfsdbcslegal.htm
old-project: ifsk
ms.assetid: 44088ca7-4a10-4002-8ae8-edd228a903f2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/FsRtlIsHpfsDbcsLegal, FsRtlIsHpfsDbcsLegal, ifsk.fsrtlishpfsdbcslegal, FsRtlIsHpfsDbcsLegal routine [Installable File System Drivers], fsrtlref_6cde5ef1-2a54-4b66-b2da-e134b5700668.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlIsHpfsDbcsLegal
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsHpfsDbcsLegal function


## -description


The <b>FsRtlIsHpfsDbcsLegal</b> routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal HPFS file name.


## -syntax


````
BOOLEAN FsRtlIsHpfsDbcsLegal(
  _In_ ANSI_STRING DbcsName,
  _In_ BOOLEAN     WildCardsPermissible,
  _In_ BOOLEAN     PathNamePermissible,
  _In_ BOOLEAN     LeadingBackslashPermissible
);
````


## -parameters




### -param DbcsName [in]

A pointer to the string to be tested.


### -param WildCardsPermissible [in]

Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.


### -param PathNamePermissible [in]

Set to <b>TRUE</b> if <i>DbcsName</i> can be a full pathname containing backslash characters, <b>FALSE</b> if it can only be a file name.


### -param LeadingBackslashPermissible [in]

Set to <b>TRUE</b> if a single leading backslash is permissible in the file or pathname, <b>FALSE</b> otherwise.


## -returns


The <b>FsRtlIsHpfsDbcsLegal</b> routine returns <b>TRUE</b> if the string is a legal HPFS file name, <b>FALSE</b> otherwise.



## -remarks


The <b>FsRtlIsHpfsDbcsLegal</b> routine determines whether the specified file name conforms to the HPFS-specific rules for legal file names. This routine will check the file name or, if <i>PathNamePermissible</i> is specified as <b>TRUE</b>, whether the whole pathname is a legal HPFS name.

HPFS file names must obey the following rules:
<ol>
<li>
The following characters are illegal in HPFS file names: 0x0000 - 0x001F, " (quotation marks), / (slash), : (colon), &lt; (less-than sign), &gt; (greater-than sign), ? (question mark), | (vertical bar or pipe), * (asterisk)

</li>
<li>
An HPFS file name cannot end in a period or a space. For example, the files "foo " and "foo." are illegal, while ".foo", " foo" and "foo.bar.foo" are legal.

</li>
<li>
An HPFS file name can contain no more than 255 bytes.

</li>
<li>
HPFS file names are case-preserving, but not case insensitive. Lowercase file names are not automatically converted to uppercase. However, case is ignored in file name comparisons.

</li>
</ol>For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsHpfsDbcsLegal routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

