---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDoesDbcsContainWildCards
title: FsRtlDoesDbcsContainWildCards function
author: windows-driver-content
description: The FsRtlDoesDbcsContainWildCards routine determines whether an ANSI or double-byte character set (DBCS) string contains wildcard characters.
old-location: ifsk\fsrtldoesdbcscontainwildcards.htm
old-project: ifsk
ms.assetid: 4a33014a-c980-4186-b7b2-68fda22fa152
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlDoesDbcsContainWildCards, FsRtlDoesDbcsContainWildCards routine [Installable File System Drivers], fsrtlref_07aa2ec1-8e37-4ffb-bd22-a3877ae8f7ee.xml, ifsk.fsrtldoesdbcscontainwildcards, ntifs/FsRtlDoesDbcsContainWildCards
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlDoesDbcsContainWildCards
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDoesDbcsContainWildCards function


## -description


The <b>FsRtlDoesDbcsContainWildCards</b> routine determines whether an ANSI or double-byte character set (DBCS) string contains wildcard characters. 


## -syntax


````
BOOLEAN FsRtlDoesDbcsContainWildCards(
  _In_ PANSI_STRING Name
);
````


## -parameters




### -param Name [in]

A pointer to the string to be checked.


## -returns



The <b>FsRtlDoesDbcsContainWildCards</b> routine returns <b>TRUE</b> if one or more wildcard characters were found, <b>FALSE</b> otherwise.




## -remarks



The following are wildcard characters: *, ?, ANSI_DOS_STAR, ANSI_DOS_DOT, and ANSI_DOS_QM.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



 

 


