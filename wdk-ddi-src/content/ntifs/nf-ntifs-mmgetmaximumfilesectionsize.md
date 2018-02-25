---
UID: NF:ntifs.MmGetMaximumFileSectionSize
title: MmGetMaximumFileSectionSize function
author: windows-driver-content
description: The MmGetMaximumFileSectionSize returns the maximum possible size of a file section for the current version of Windows.
old-location: ifsk\mmgetmaximumfilesectionsize.htm
old-project: ifsk
ms.assetid: 5B3E5B33-EFED-485A-A62A-7A54322408AC
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, G, M, MmGetMaximumFileSectionSize, MmGetMaximumFileSectionSize routine [Installable File System Drivers], S, a, c, e, i, ifsk.mmgetmaximumfilesectionsize, l, m, n, ntifs/MmGetMaximumFileSectionSize, o, t, u, x, z"
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmGetMaximumFileSectionSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# MmGetMaximumFileSectionSize function


## -description


The <b>MmGetMaximumFileSectionSize</b> returns the maximum possible size of a file section for the current version of Windows.


## -syntax


````
ULONGLONG MmGetMaximumFileSectionSize(void);
````


## -parameters






## -returns



The maximum file section size supported by the current version of Windows.



