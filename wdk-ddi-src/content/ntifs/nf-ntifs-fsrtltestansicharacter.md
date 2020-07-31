---
UID: NF:ntifs.FsRtlTestAnsiCharacter
title: FsRtlTestAnsiCharacter macro (ntifs.h)
description: The FsRtlTestAnsiCharacter macro determines whether an ANSI or double-byte character set (DBCS) character meets the specified criteria.
old-location: ifsk\fsrtltestansicharacter.htm
tech.root: ifsk
ms.assetid: b667f0c9-7746-432e-ae58-3fe5b48309e0
ms.date: 04/16/2018
keywords: ["FsRtlTestAnsiCharacter macro"]
ms.keywords: FsRtlTestAnsiCharacter, FsRtlTestAnsiCharacter function [Installable File System Drivers], fsrtlref_7ef89c09-f42e-433a-90bf-59452fd1b7c4.xml, ifsk.fsrtltestansicharacter, ntifs/FsRtlTestAnsiCharacter
f1_keywords:
 - "ntifs/FsRtlTestAnsiCharacter"
 - "FsRtlTestAnsiCharacter"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlTestAnsiCharacter
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

<p>Default value to be returned if the value of <i>(SCHAR *)Character</i> is < 0.</p>


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






## -remarks



For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegal">FsRtlIsAnsiCharacterLegal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalfat">FsRtlIsAnsiCharacterLegalFat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalhpfs">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalntfs">FsRtlIsAnsiCharacterLegalNtfs</a>
 

 

