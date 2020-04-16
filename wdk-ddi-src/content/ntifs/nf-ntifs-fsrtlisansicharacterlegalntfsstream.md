---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalNtfsStream
title: FsRtlIsAnsiCharacterLegalNtfsStream macro (ntifs.h)
description: The FsRtlIsAnsiCharacterLegalNtfsStream macro determines whether an ANSI character is legal for NTFS stream names.
old-location: ifsk\fsrtlisansicharacterlegalntfsstream.htm
tech.root: ifsk
ms.assetid: 2bcfa3b3-8a83-460b-9b44-1188fceb3849
ms.date: 04/16/2018
keywords: ["FsRtlIsAnsiCharacterLegalNtfsStream macro"]
ms.keywords: FsRtlIsAnsiCharacterLegalNtfsStream, FsRtlIsAnsiCharacterLegalNtfsStream function [Installable File System Drivers], fsrtlref_0dc6f0d3-6f38-4861-89d6-15cab783a959.xml, ifsk.fsrtlisansicharacterlegalntfsstream, ntifs/FsRtlIsAnsiCharacterLegalNtfsStream
f1_keywords:
 - "ntifs/FsRtlIsAnsiCharacterLegalNtfsStream"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlIsAnsiCharacterLegalNtfsStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsAnsiCharacterLegalNtfsStream macro


## -description


The <b>FsRtlIsAnsiCharacterLegalNtfsStream</b> macro determines whether an ANSI character is legal for NTFS stream names. 


## -parameters




### -param C

<p>Pointer to the character to be tested. </p>


### -param WILD_OK

<p>Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise. </p>






## -remarks



For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegal">FsRtlIsAnsiCharacterLegal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalfat">FsRtlIsAnsiCharacterLegalFat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalhpfs">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalntfs">FsRtlIsAnsiCharacterLegalNtfs</a>
 

 

