---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegal
title: FsRtlIsAnsiCharacterLegal macro (ntifs.h)
description: The FsRtlIsAnsiCharacterLegal macro determines whether a character is a legal ANSI character.
old-location: ifsk\fsrtlisansicharacterlegal.htm
tech.root: ifsk
ms.assetid: e270e4a9-90dc-4e9b-abdf-079c331ad71c
ms.date: 04/16/2018
ms.keywords: FsRtlIsAnsiCharacterLegal, FsRtlIsAnsiCharacterLegal function [Installable File System Drivers], fsrtlref_dad0349c-b705-4a0a-a1ea-359517e65eae.xml, ifsk.fsrtlisansicharacterlegal, ntifs/FsRtlIsAnsiCharacterLegal
ms.topic: macro
f1_keywords:
 - "ntifs/FsRtlIsAnsiCharacterLegal"
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
- FsRtlIsAnsiCharacterLegal
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsAnsiCharacterLegal macro


## -description


The <b>FsRtlIsAnsiCharacterLegal</b> macro determines whether a character is a legal ANSI character.


## -parameters




### -param C

<p>The character to be tested.</p>


### -param FLAGS

<p>Combination of one or more of the following flag values:</p>
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
        <p>Valid characters for high-performance file system (HPFS) file names are legal.</p>
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



To be a legal ANSI character, a character must be present in the ANSI legal character array and must satisfy the input flag settings. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlisansicharacterlegalfat">FsRtlIsAnsiCharacterLegalFat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlisansicharacterlegalhpfs">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlisansicharacterlegalntfs">FsRtlIsAnsiCharacterLegalNtfs</a>
 

 

