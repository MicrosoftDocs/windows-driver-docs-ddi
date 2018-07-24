---
UID: NF:ntifs.FsRtlIsLeadDbcsCharacter
title: FsRtlIsLeadDbcsCharacter macro
author: windows-driver-content
description: The FsRtlIsLeadDbcsCharacter macro determines whether a character is a lead byte (the first byte of a character) in a double-byte character set (DBCS).
old-location: ifsk\fsrtlisleaddbcscharacter.htm
tech.root: ifsk
ms.assetid: 3cbae037-6205-4315-8ff7-0c67a91c4c69
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlIsLeadDbcsCharacter, FsRtlIsLeadDbcsCharacter function [Installable File System Drivers], fsrtlref_758a5e18-3446-43c4-8cce-baecdf727f98.xml, ifsk.fsrtlisleaddbcscharacter, ntifs/FsRtlIsLeadDbcsCharacter
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
-	FsRtlIsLeadDbcsCharacter
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

TBD






#### - DbcsCharacter [in]

The character to be tested.


## -remarks



Lead bytes are unique to double-byte character sets. A lead byte introduces a double-byte character. Lead bytes occupy a specific range of byte values. The <b>FsRtlIsLeadDbcsCharacter</b> macro uses the system code page to check lead-byte ranges.  

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545877">FsRtlDissectDbcs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545891">FsRtlDoesDbcsContainWildCards</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546803">FsRtlIsDbcsInExpression</a>
 

 

