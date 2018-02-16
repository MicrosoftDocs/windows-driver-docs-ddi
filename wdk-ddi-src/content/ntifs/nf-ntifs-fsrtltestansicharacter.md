---
UID: NF:ntifs.FsRtlTestAnsiCharacter
title: FsRtlTestAnsiCharacter macro
author: windows-driver-content
description: The FsRtlTestAnsiCharacter macro determines whether an ANSI or double-byte character set (DBCS) character meets the specified criteria.
old-location: ifsk\fsrtltestansicharacter.htm
old-project: ifsk
ms.assetid: b667f0c9-7746-432e-ae58-3fe5b48309e0
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlTestAnsiCharacter function [Installable File System Drivers], fsrtlref_7ef89c09-f42e-433a-90bf-59452fd1b7c4.xml, ntifs/FsRtlTestAnsiCharacter, FsRtlTestAnsiCharacter, ifsk.fsrtltestansicharacter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.lib: ntifs.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FsRtlTestAnsiCharacter
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlTestAnsiCharacter macro


## -description


The<b> FsRtlTestAnsiCharacter</b> macro determines whether an ANSI or double-byte character set (DBCS) character meets the specified criteria.


## -syntax


````
BOOLEAN FsRtlTestAnsiCharacter(
   PSCHAR  *Character,
   BOOLEAN DefaultReturnValue,
   BOOLEAN WildCardsPermissible,
   UCHAR   Flags
);
````


## -parameters




### -param C

TBD


### -param DEFAULT_RET

TBD


### -param WILD_OK

TBD


### -param FLAGS

TBD






#### - Character

Pointer to the character to be tested.


#### - DefaultReturnValue

Default value to be returned if the value of <i>(SCHAR *)Character</i> is &lt; 0.


#### - Flags

Combination of one or more of the flag values described following.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FSRTL_FAT_LEGAL

</td>
<td>
Valid characters for FAT file names are legal.

</td>
</tr>
<tr>
<td>
FSRTL_HPFS_LEGAL

</td>
<td>
Valid characters for HPFS file names are legal.

</td>
</tr>
<tr>
<td>
FSRTL_NTFS_LEGAL

</td>
<td>
Valid characters for NTFS file names are legal.

</td>
</tr>
<tr>
<td>
FSRTL_WILD_CHARACTER

</td>
<td>
Wildcard characters are legal.

</td>
</tr>
<tr>
<td>
FSRTL_OLE_LEGAL

</td>
<td>
Valid characters for NTFS stream names are legal. 

</td>
</tr>
<tr>
<td>
FSRTL_NTFS_STREAM_LEGAL

</td>
<td>
FSRTL_NTFS_LEGAL | FSRTL_OLE_LEGAL

</td>
</tr>
</table>
 


#### - WildCardsPermissible

Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.


## -remarks



For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegal.md">FsRtlIsAnsiCharacterLegal</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalfat.md">FsRtlIsAnsiCharacterLegalFat</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalntfs.md">FsRtlIsAnsiCharacterLegalNtfs</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalhpfs.md">FsRtlIsAnsiCharacterLegalHpfs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlTestAnsiCharacter function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

