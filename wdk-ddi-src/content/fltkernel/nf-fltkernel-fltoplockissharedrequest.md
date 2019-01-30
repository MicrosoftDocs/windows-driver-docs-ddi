---
UID: NF:fltkernel.FltOplockIsSharedRequest
title: FltOplockIsSharedRequest function (fltkernel.h)
description: The FltOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock.
old-location: ifsk\fltoplockissharedrequest.htm
tech.root: ifsk
ms.assetid: 5387e22a-88df-413f-a6d1-2e208381df67
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_93f74880-eb0d-4040-82a0-e0cb4bfb2cba.xml, FltOplockIsSharedRequest, FltOplockIsSharedRequest routine [Installable File System Drivers], fltkernel/FltOplockIsSharedRequest, ifsk.fltoplockissharedrequest
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltOplockIsSharedRequest routine is available starting with Windows 7.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltOplockIsSharedRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltOplockIsSharedRequest function


## -description


The <b>FltOplockIsSharedRequest</b> routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. 


## -parameters




### -param CallbackData [in]

A pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the I/O operation. The caller must ensure that the I/O operation has a major code of IRP_MJ_FILE_SYSTEM_CONTROL and a minor code of IRP_MN_USER_FS_REQUEST. 


## -returns



<b>FltOplockIsSharedRequest</b> returns <b>TRUE</b> if the oplock request is for a shared oplock (that is, a level 2, R, or RH oplock). <b>FltOplockIsSharedRequest</b> returns <b>FALSE</b> if the oplock request is not for a shared oplock or if the I/O operation is not an oplock request. For more information about oplock types, see <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Oplock Semantics Overview</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547128">FsRtlOplockIsSharedRequest</a>
 

 

