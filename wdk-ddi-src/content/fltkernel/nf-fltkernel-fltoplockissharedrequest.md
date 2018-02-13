---
UID: NF:fltkernel.FltOplockIsSharedRequest
title: FltOplockIsSharedRequest function
author: windows-driver-content
description: The FltOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock.
old-location: ifsk\fltoplockissharedrequest.htm
old-project: ifsk
ms.assetid: 5387e22a-88df-413f-a6d1-2e208381df67
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltkernel/FltOplockIsSharedRequest, FltOplockIsSharedRequest, ifsk.fltoplockissharedrequest, FltOplockIsSharedRequest routine [Installable File System Drivers], FltApiRef_e_to_o_93f74880-eb0d-4040-82a0-e0cb4bfb2cba.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltOplockIsSharedRequest
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltOplockIsSharedRequest function


## -description


The <b>FltOplockIsSharedRequest</b> routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. 


## -syntax


````
BOOLEAN FltOplockIsSharedRequest(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

A pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. The caller must ensure that the I/O operation has a major code of IRP_MJ_FILE_SYSTEM_CONTROL and a minor code of IRP_MN_USER_FS_REQUEST. 


## -returns



<b>FltOplockIsSharedRequest</b> returns <b>TRUE</b> if the oplock request is for a shared oplock (that is, a level 2, R, or RH oplock). <b>FltOplockIsSharedRequest</b> returns <b>FALSE</b> if the oplock request is not for a shared oplock or if the I/O operation is not an oplock request. For more information about oplock types, see <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Oplock Semantics Overview</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockissharedrequest.md">FsRtlOplockIsSharedRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockIsSharedRequest routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

