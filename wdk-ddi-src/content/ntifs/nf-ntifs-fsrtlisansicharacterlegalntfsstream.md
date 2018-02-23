---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalNtfsStream
title: FsRtlIsAnsiCharacterLegalNtfsStream macro
author: windows-driver-content
description: The FsRtlIsAnsiCharacterLegalNtfsStream macro determines whether an ANSI character is legal for NTFS stream names.
old-location: ifsk\fsrtlisansicharacterlegalntfsstream.htm
old-project: ifsk
ms.assetid: 2bcfa3b3-8a83-460b-9b44-1188fceb3849
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fsrtlref_0dc6f0d3-6f38-4861-89d6-15cab783a959.xml, ntifs/FsRtlIsAnsiCharacterLegalNtfsStream, FsRtlIsAnsiCharacterLegalNtfsStream function [Installable File System Drivers], ifsk.fsrtlisansicharacterlegalntfsstream, FsRtlIsAnsiCharacterLegalNtfsStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: ntifs.h
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FsRtlIsAnsiCharacterLegalNtfsStream
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsAnsiCharacterLegalNtfsStream macro


## -description


The <b>FsRtlIsAnsiCharacterLegalNtfsStream</b> macro determines whether an ANSI character is legal for NTFS stream names. 


## -syntax


````
BOOLEAN FsRtlIsAnsiCharacterLegalNtfsStream(
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

<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalhpfs.md">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalntfs.md">FsRtlIsAnsiCharacterLegalNtfs</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegalfat.md">FsRtlIsAnsiCharacterLegalFat</a>



<a href="..\ntifs\nf-ntifs-fsrtlisansicharacterlegal.md">FsRtlIsAnsiCharacterLegal</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsAnsiCharacterLegalNtfsStream function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

