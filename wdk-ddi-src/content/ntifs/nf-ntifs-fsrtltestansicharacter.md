---
UID: NF:ntifs.FsRtlTestAnsiCharacter
title: FsRtlTestAnsiCharacter macro
author: windows-driver-content
description: The FsRtlTestAnsiCharacter macro determines whether an ANSI or double-byte character set (DBCS) character meets the specified criteria.
old-location: ifsk\fsrtltestansicharacter.htm
tech.root: ifsk
ms.assetid: b667f0c9-7746-432e-ae58-3fe5b48309e0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlTestAnsiCharacter, FsRtlTestAnsiCharacter function [Installable File System Drivers], fsrtlref_7ef89c09-f42e-433a-90bf-59452fd1b7c4.xml, ifsk.fsrtltestansicharacter, ntifs/FsRtlTestAnsiCharacter
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlTestAnsiCharacter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlTestAnsiCharacter macro


## -description


The<b> FsRtlTestAnsiCharacter</b> macro determines whether an ANSI or double-byte character set (DBCS) character meets the specified criteria.


## -parameters




### -param C

<p>Pointer to the character to be tested.</p>


### -param DEFAULT_RET

<p>Default value to be returned if the value of <i>(SCHAR *)Character</i> is &lt; 0.</p>


### -param WILD_OK

<p>Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.</p>


### -param FLAGS

<p>Combination of one or more of the flag values described following.</p>
  <table>
    <tr>
      <th>Flag</th>
      <th>Meaning</th>
    </tr>
    <tr>
      <td>
        <p>FSRTL_FAT_LEGAL</p>
      </td>
      <td>
        <p>Valid characters for FAT file names are legal.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FSRTL_HPFS_LEGAL</p>
      </td>
      <td>
        <p>Valid characters for HPFS file names are legal.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FSRTL_NTFS_LEGAL</p>
      </td>
      <td>
        <p>Valid characters for NTFS file names are legal.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FSRTL_WILD_CHARACTER</p>
      </td>
      <td>
        <p>Wildcard characters are legal.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FSRTL_OLE_LEGAL</p>
      </td>
      <td>
        <p>Valid characters for NTFS stream names are legal. </p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FSRTL_NTFS_STREAM_LEGAL</p>
      </td>
      <td>
        <p>FSRTL_NTFS_LEGAL | FSRTL_OLE_LEGAL</p>
      </td>
    </tr>
  </table>
  <p> </p>






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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546731">FsRtlIsAnsiCharacterLegal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546735">FsRtlIsAnsiCharacterLegalFat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546761">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546768">FsRtlIsAnsiCharacterLegalNtfs</a>
 

 

