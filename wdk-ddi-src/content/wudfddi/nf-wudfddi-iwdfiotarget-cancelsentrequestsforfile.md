---
UID: NF:wudfddi.IWDFIoTarget.CancelSentRequestsForFile
title: IWDFIoTarget::CancelSentRequestsForFile method
author: windows-driver-content
description: The CancelSentRequestsForFile method cancels all I/O requests that have been sent on behalf of the specified file object.
old-location: wdf\iwdfiotarget_cancelsentrequestsforfile.htm
old-project: wdf
ms.assetid: df008ee8-352f-4655-b4c0-750eeb281e6a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, C, CancelSentRequestsForFile method, CancelSentRequestsForFile method, IWDFIoTarget interface, CancelSentRequestsForFile,IWDFIoTarget.CancelSentRequestsForFile, D, F, I, IWDFIoTarget, IWDFIoTarget interface, CancelSentRequestsForFile method, IWDFIoTarget::CancelSentRequestsForFile, R, S, T, UMDFIoTargetObjectRef_d2a2405f-312e-4e3c-8ffa-8568438805b0.xml, W, a, c, e, g, i, l, n, o, q, r, s, t, u, umdf.iwdfiotarget_cancelsentrequestsforfile, wdf.iwdfiotarget_cancelsentrequestsforfile, wudfddi/IWDFIoTarget::CancelSentRequestsForFile"
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoTarget.CancelSentRequestsForFile
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoTarget::CancelSentRequestsForFile method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CancelSentRequestsForFile</b> method cancels all I/O requests that have been sent on behalf of the specified file object.


## -syntax


````
void CancelSentRequestsForFile(
  [in] IWDFFile *pFile
);
````


## -parameters




### -param pFile [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object to cancel all I/O requests for. 


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTarget::CancelSentRequestsForFile method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

