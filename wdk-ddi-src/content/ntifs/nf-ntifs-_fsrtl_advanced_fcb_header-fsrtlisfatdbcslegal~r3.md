---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlIsFatDbcsLegal~r3
title: FsRtlIsFatDbcsLegal function
author: windows-driver-content
description: The FsRtlIsFatDbcsLegal routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal FAT file name.
old-location: ifsk\fsrtlisfatdbcslegal.htm
old-project: ifsk
ms.assetid: 1ba94491-718b-41bf-bc22-2d99ba34c6af
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlIsFatDbcsLegal
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
req.alt-api: FsRtlIsFatDbcsLegal
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlIsFatDbcsLegal function



## -description
The <b>FsRtlIsFatDbcsLegal</b> routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal FAT file name.



## -syntax

````
BOOLEAN FsRtlIsFatDbcsLegal(
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

Set to <b>TRUE</b> if <i>DbcsName</i> can be a full pathname containing backslash characters, <b>FALSE</b> if it can only be file name.


### -param LeadingBackslashPermissible [in]

Set to <b>TRUE</b> if a single leading backslash is permissible in the file or pathname, <b>FALSE</b> otherwise.


## -returns
The <b>FsRtlIsFatDbcsLegal</b> routine returns <b>TRUE</b> if the string is a legal FAT file name, <b>FALSE</b> otherwise.


## -remarks
The <b>FsRtlIsFatDbcsLegal</b> routine determines whether the specified file name conforms to the FAT-specific rules for legal file names. This routine will check the file name or, if <i>PathNamePermissible</i> is specified as <b>TRUE</b>, whether the whole pathname is a legal FAT name.

FAT file names must obey the following rules:

The following characters are illegal in FAT file names: 0x00-0x1F, " (straight quotation marks), / (slash), : (colon), | (vertical bar or pipe), + (plus), , (comma), ; (semicolon), = (equal sign), [ ] (brackets)

A FAT file name is either of the form N.E or just N, where N is a string of one to eight bytes and E is a string of one to three bytes conformant to rule one. In addition, neither N nor E may contain a . (period) or end with a space character. For example, the files ".foo", "foo.", and "foo .b" are illegal, while "foo. b" and " bar" are legal.

FAT file names are case insensitive. Lowercase names are automatically converted to uppercase. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsFatDbcsLegal routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

