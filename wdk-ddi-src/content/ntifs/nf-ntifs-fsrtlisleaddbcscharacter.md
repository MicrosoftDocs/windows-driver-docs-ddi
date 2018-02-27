---
UID: NF:ntifs.FsRtlIsLeadDbcsCharacter
title: FsRtlIsLeadDbcsCharacter macro
author: windows-driver-content
description: The FsRtlIsLeadDbcsCharacter macro determines whether a character is a lead byte (the first byte of a character) in a double-byte character set (DBCS).
old-location: ifsk\fsrtlisleaddbcscharacter.htm
old-project: ifsk
ms.assetid: 3cbae037-6205-4315-8ff7-0c67a91c4c69
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
-	FsRtlIsLeadDbcsCharacter
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsLeadDbcsCharacter macro


## -description


The <b>FsRtlIsLeadDbcsCharacter</b> macro determines whether a character is a lead byte (the first byte of a character) in a double-byte character set (DBCS). 


## -syntax


````
BOOLEAN FsRtlIsLeadDbcsCharacter(
  _In_ UCHAR DbcsCharacter
);
````


## -parameters




### -param DBCS_CHAR

TBD






#### - DbcsCharacter [in]

The character to be tested.


## -remarks



Lead bytes are unique to double-byte character sets. A lead byte introduces a double-byte character. Lead bytes occupy a specific range of byte values. The <b>FsRtlIsLeadDbcsCharacter</b> macro uses the system code page to check lead-byte ranges.  

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldoesdbcscontainwildcards.md">FsRtlDoesDbcsContainWildCards</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisdbcsinexpression~r1.md">FsRtlIsDbcsInExpression</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldissectdbcs~r2.md">FsRtlDissectDbcs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsLeadDbcsCharacter function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

