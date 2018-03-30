---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalNtfs
title: FsRtlIsAnsiCharacterLegalNtfs macro
author: windows-driver-content
description: The FsRtlIsAnsiCharacterLegalNtfs macro determines whether an ANSI character is legal for NTFS file names.
old-location: ifsk\fsrtlisansicharacterlegalntfs.htm
old-project: ifsk
ms.assetid: 05d03799-752d-4f59-b96e-1a6d91bee8c4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlIsAnsiCharacterLegalNtfs, FsRtlIsAnsiCharacterLegalNtfs function [Installable File System Drivers], fsrtlref_9150101b-7411-4de2-afd5-0b928ed0e6b1.xml, ifsk.fsrtlisansicharacterlegalntfs, ntifs/FsRtlIsAnsiCharacterLegalNtfs
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
-	FsRtlIsAnsiCharacterLegalNtfs
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsAnsiCharacterLegalNtfs macro


## -description


The <b>FsRtlIsAnsiCharacterLegalNtfs</b> macro determines whether an ANSI character is legal for NTFS file names.


## -parameters




### -param C

TBD


### -param WILD_OK

TBD






#### - Character

Pointer to the character to be tested.


#### - WildCardsPermissible

Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.


## -remarks



For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546731">FsRtlIsAnsiCharacterLegal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546735">FsRtlIsAnsiCharacterLegalFat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546761">FsRtlIsAnsiCharacterLegalHpfs</a>
 

 

