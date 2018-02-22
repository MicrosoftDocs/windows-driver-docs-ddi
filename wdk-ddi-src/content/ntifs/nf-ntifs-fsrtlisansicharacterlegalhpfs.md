---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalHpfs
title: FsRtlIsAnsiCharacterLegalHpfs macro
author: windows-driver-content
description: The FsRtlIsAnsiCharacterLegalHpfs macro determines whether an ANSI character is legal for HPFS file names.
old-location: ifsk\fsrtlisansicharacterlegalhpfs.htm
old-project: ifsk
ms.assetid: 7c7e79ff-badf-4f5b-bab6-5b9fa1656e23
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlIsAnsiCharacterLegalHpfs, ntifs/FsRtlIsAnsiCharacterLegalHpfs, fsrtlref_063585f7-66ed-427f-aaea-c19d9d10fb5c.xml, FsRtlIsAnsiCharacterLegalHpfs function [Installable File System Drivers], ifsk.fsrtlisansicharacterlegalhpfs
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
-	FsRtlIsAnsiCharacterLegalHpfs
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsAnsiCharacterLegalHpfs macro


## -description


The <b>FsRtlIsAnsiCharacterLegalHpfs</b> macro determines whether an ANSI character is legal for HPFS file names.


## -syntax


````
BOOLEAN FsRtlIsAnsiCharacterLegalHpfs(
   PSCHAR  *Character,
   BOOLEAN WildCardsPermissible
);
````


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

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalfat.md">FsRtlIsAnsiCharacterLegalFat</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalntfs.md">FsRtlIsAnsiCharacterLegalNtfs</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegal.md">FsRtlIsAnsiCharacterLegal</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsAnsiCharacterLegalHpfs function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

