---
UID: NF:ntifs.FsRtlIsLeadDbcsCharacter
title: FsRtlIsLeadDbcsCharacter macro (ntifs.h)
description: The FsRtlIsLeadDbcsCharacter macro determines whether a character is a lead byte (the first byte of a character) in a double-byte character set (DBCS).
old-location: ifsk\fsrtlisleaddbcscharacter.htm
tech.root: ifsk
ms.assetid: 3cbae037-6205-4315-8ff7-0c67a91c4c69
ms.date: 04/16/2018
ms.keywords: FsRtlIsLeadDbcsCharacter, FsRtlIsLeadDbcsCharacter function [Installable File System Drivers], fsrtlref_758a5e18-3446-43c4-8cce-baecdf727f98.xml, ifsk.fsrtlisleaddbcscharacter, ntifs/FsRtlIsLeadDbcsCharacter
f1_keywords:
 - "ntifs/FsRtlIsLeadDbcsCharacter"
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
- FsRtlIsLeadDbcsCharacter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsLeadDbcsCharacter macro


## -description


The <b>FsRtlIsLeadDbcsCharacter</b> macro determines whether a character is a lead byte (the first byte of a character) in a double-byte character set (DBCS). 


## -parameters




### -param DBCS_CHAR

<p>The character to be tested.</p>






## -remarks



Lead bytes are unique to double-byte character sets. A lead byte introduces a double-byte character. Lead bytes occupy a specific range of byte values. The <b>FsRtlIsLeadDbcsCharacter</b> macro uses the system code page to check lead-byte ranges.  

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtldissectdbcs">FsRtlDissectDbcs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtldoesdbcscontainwildcards">FsRtlDoesDbcsContainWildCards</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisdbcsinexpression">FsRtlIsDbcsInExpression</a>
 

 

