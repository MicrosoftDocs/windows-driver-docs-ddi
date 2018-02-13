---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetCompletionStatus
title: IWDFRequestCompletionParams::GetCompletionStatus method
author: windows-driver-content
description: The GetCompletionStatus method retrieves the completion status of an I/O request.
old-location: wdf\iwdfrequestcompletionparams_getcompletionstatus.htm
old-project: wdf
ms.assetid: 8959fc25-2477-485a-aa40-10d6228cb476
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi/IWDFRequestCompletionParams::GetCompletionStatus, GetCompletionStatus method, IWDFRequestCompletionParams interface, umdf.iwdfrequestcompletionparams_getcompletionstatus, IWDFRequestCompletionParams, IWDFRequestCompletionParams interface, GetCompletionStatus method, GetCompletionStatus method, IWDFRequestCompletionParams::GetCompletionStatus, UMDFRequestObjectRef_b3664f4d-fdb1-425f-be0a-3b4150762b9d.xml, wdf.iwdfrequestcompletionparams_getcompletionstatus, GetCompletionStatus
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
-	IWDFRequestCompletionParams.GetCompletionStatus
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFRequestCompletionParams::GetCompletionStatus method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletionStatus</b> method retrieves the completion status of an I/O request.


## -syntax


````
HRESULT GetCompletionStatus();
````


## -parameters






## -returns



<b>GetCompletionStatus</b> returns S_OK for a successful completion status. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRequestCompletionParams::GetCompletionStatus method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

