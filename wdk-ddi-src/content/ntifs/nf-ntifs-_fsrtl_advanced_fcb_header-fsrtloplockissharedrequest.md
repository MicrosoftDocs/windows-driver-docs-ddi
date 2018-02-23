---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockIsSharedRequest
title: FsRtlOplockIsSharedRequest function
author: windows-driver-content
description: The FsRtlOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock.
old-location: ifsk\fsrtloplockissharedrequest.htm
old-project: ifsk
ms.assetid: 21cc6f5b-d7c4-405d-9c98-c17e2f669cda
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fsrtlref_e79317ec-0086-4387-8f80-a7a1e44aba1c.xml, ntifs/FsRtlOplockIsSharedRequest, FsRtlOplockIsSharedRequest routine [Installable File System Drivers], FsRtlOplockIsSharedRequest, ifsk.fsrtloplockissharedrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlOplockIsSharedRequest
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlOplockIsSharedRequest function


## -description


The <b>FsRtlOplockIsSharedRequest</b> routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. 


## -syntax


````
BOOLEAN FsRtlOplockIsSharedRequest(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to the IRP that declares the requested operation. The caller must ensure that the IRP has a major code of IRP_MJ_FILE_SYSTEM_CONTROL and a minor code of IRP_MN_USER_FS_REQUEST. 


## -returns



<b>FsRtlOplockIsSharedRequest</b> returns <b>TRUE</b> if the oplock request is for a shared oplock (that is, a level 2, R, or RH oplock). <b>FsRtlOplockIsSharedRequest</b> returns <b>FALSE</b> if the oplock request is not for a shared oplock or if the IRP is not an oplock request. For more information about oplock types, see the Oplock Semantics <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Overview</a> page. Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltoplockissharedrequest.md">FltOplockIsSharedRequest</a> instead of <b>FsRtlOplockIsSharedRequest</b>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltoplockissharedrequest.md">FltOplockIsSharedRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlOplockIsSharedRequest routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

