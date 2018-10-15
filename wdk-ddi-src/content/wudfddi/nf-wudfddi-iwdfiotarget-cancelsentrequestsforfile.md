---
UID: NF:wudfddi.IWDFIoTarget.CancelSentRequestsForFile
title: IWDFIoTarget::CancelSentRequestsForFile
author: windows-driver-content
description: The CancelSentRequestsForFile method cancels all I/O requests that have been sent on behalf of the specified file object.
old-location: wdf\iwdfiotarget_cancelsentrequestsforfile.htm
tech.root: wdf
ms.assetid: df008ee8-352f-4655-b4c0-750eeb281e6a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CancelSentRequestsForFile, CancelSentRequestsForFile method, CancelSentRequestsForFile method,IWDFIoTarget interface, IWDFIoTarget interface,CancelSentRequestsForFile method, IWDFIoTarget.CancelSentRequestsForFile, IWDFIoTarget::CancelSentRequestsForFile, UMDFIoTargetObjectRef_d2a2405f-312e-4e3c-8ffa-8568438805b0.xml, umdf.iwdfiotarget_cancelsentrequestsforfile, wdf.iwdfiotarget_cancelsentrequestsforfile, wudfddi/IWDFIoTarget::CancelSentRequestsForFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoTarget.CancelSentRequestsForFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget::CancelSentRequestsForFile


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CancelSentRequestsForFile</b> method cancels all I/O requests that have been sent on behalf of the specified file object.


## -parameters




### -param pFile [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the file object to cancel all I/O requests for. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>
 

 

