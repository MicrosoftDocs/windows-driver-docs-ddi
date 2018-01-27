---
UID: NF:ntifs.FsRtlQueryCachedVdl
title: FsRtlQueryCachedVdl function
author: windows-driver-content
description: The current valid data length (VDL) for a cached file is retrieved with the FsRtlQueryCachedVdl routine.
old-location: ifsk\fsrtlquerycachedvdl.htm
old-project: ifsk
ms.assetid: 5D4F3D70-6E2B-4B2E-91A4-6852AF8FEAD0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlQueryCachedVdl routine [Installable File System Drivers], ifsk.fsrtlquerycachedvdl, FsRtlQueryCachedVdl, ntifs/FsRtlQueryCachedVdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
-	FsRtlQueryCachedVdl
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlQueryCachedVdl function


## -description


The current valid data length (VDL) for a cached file is retrieved with the <b>FsRtlQueryCachedVdl</b> routine.


## -syntax


````
NTSTATUS FsRtlQueryCachedVdl(
  _In_  PFILE_OBJECT FileObject,
  _Out_ PLONGLONG    Vdl
);
````


## -parameters




### -param FileObject [in]

The file object to retrieve the cached VDL for.


### -param Vdl [out]

 A pointer to a caller supplied value which receives the VDL.


## -returns


<b>FsRtlQueryCachedVdl</b> returns <b>STATUS_SUCCESS</b> if the cached VDL is obtained successfully for the <i>FileObject</i> specified. Otherwise, another appropriate <b>NTSTATUS</b> value is returned.



## -remarks


The <b>FsRtlQueryCachedVdl</b> routine will return the VDL for a full span file region. This is a region beginning at an offset of 0 and having a length of <b>MAXLONGLONG</b>.


