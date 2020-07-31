---
UID: NF:ntifs.FsRtlOplockIsSharedRequest
title: FsRtlOplockIsSharedRequest function (ntifs.h)
description: The FsRtlOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock.
old-location: ifsk\fsrtloplockissharedrequest.htm
tech.root: ifsk
ms.assetid: 21cc6f5b-d7c4-405d-9c98-c17e2f669cda
ms.date: 04/16/2018
keywords: ["FsRtlOplockIsSharedRequest function"]
ms.keywords: FsRtlOplockIsSharedRequest, FsRtlOplockIsSharedRequest routine [Installable File System Drivers], fsrtlref_e79317ec-0086-4387-8f80-a7a1e44aba1c.xml, ifsk.fsrtloplockissharedrequest, ntifs/FsRtlOplockIsSharedRequest
f1_keywords:
 - "ntifs/FsRtlOplockIsSharedRequest"
 - "FsRtlOplockIsSharedRequest"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockIsSharedRequest routine is available starting with Windows 7.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlOplockIsSharedRequest
targetos: Windows
req.typenames: 
---

# FsRtlOplockIsSharedRequest function


## -description


The <b>FsRtlOplockIsSharedRequest</b> routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. 


## -parameters




### -param Irp [in]

A pointer to the IRP that declares the requested operation. The caller must ensure that the IRP has a major code of IRP_MJ_FILE_SYSTEM_CONTROL and a minor code of IRP_MN_USER_FS_REQUEST. 


## -returns



<b>FsRtlOplockIsSharedRequest</b> returns <b>TRUE</b> if the oplock request is for a shared oplock (that is, a level 2, R, or RH oplock). <b>FsRtlOplockIsSharedRequest</b> returns <b>FALSE</b> if the oplock request is not for a shared oplock or if the IRP is not an oplock request. For more information about oplock types, see the Oplock Semantics <a href="https://docs.microsoft.com/windows-hardware/drivers/image/overview">Overview</a> page. Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockissharedrequest">FltOplockIsSharedRequest</a> instead of <b>FsRtlOplockIsSharedRequest</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltoplockissharedrequest">FltOplockIsSharedRequest</a>
 

 

