---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDoesNameContainWildCards
title: FsRtlDoesNameContainWildCards function
author: windows-driver-content
description: The FsRtlDoesNameContainWildCards routine determines whether a Unicode string contains wildcard characters.
old-location: ifsk\fsrtldoesnamecontainwildcards.htm
old-project: ifsk
ms.assetid: a2bcf1c0-a6c7-4bf3-bce6-9a661f2ab2e1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fsrtldoesnamecontainwildcards, ntifs/FsRtlDoesNameContainWildCards, fsrtlref_1b39ef0b-3ec3-4d4b-9ee6-abe674e359aa.xml, FsRtlDoesNameContainWildCards, FsRtlDoesNameContainWildCards routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlDoesNameContainWildCards
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDoesNameContainWildCards function


## -description


The <b>FsRtlDoesNameContainWildCards</b> routine determines whether a Unicode string contains wildcard characters. 


## -syntax


````
BOOLEAN FsRtlDoesNameContainWildCards(
  _In_ PUNICODE_STRING Name
);
````


## -parameters




### -param Name [in]

A pointer to the string to be checked.


## -returns



<b>FsRtlDoesNameContainWildCards</b> returns <b>TRUE</b> if one or more wildcard characters were found, <b>FALSE</b> otherwise.




## -remarks



The following are wildcard characters: *, ?, ANSI_DOS_STAR, ANSI_DOS_DOT, and ANSI_DOS_QM.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlDoesNameContainWildCards routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

