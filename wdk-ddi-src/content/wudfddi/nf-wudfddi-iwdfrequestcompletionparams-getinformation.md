---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetInformation
title: IWDFRequestCompletionParams::GetInformation method
author: windows-driver-content
description: The GetInformation method retrieves information that is associated with the completion of an I/O request.
old-location: wdf\iwdfrequestcompletionparams_getinformation.htm
old-project: wdf
ms.assetid: 6dd47575-0da3-4038-81aa-ac955c00f08d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetInformation method, wdf.iwdfrequestcompletionparams_getinformation, IWDFRequestCompletionParams, GetInformation, wudfddi/IWDFRequestCompletionParams::GetInformation, umdf.iwdfrequestcompletionparams_getinformation, UMDFRequestObjectRef_f014a31c-ac37-419d-a318-31d910c646b1.xml, IWDFRequestCompletionParams::GetInformation, IWDFRequestCompletionParams interface, GetInformation method, GetInformation method, IWDFRequestCompletionParams interface
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
-	IWDFRequestCompletionParams.GetInformation
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRequestCompletionParams::GetInformation method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInformation</b> method retrieves information that is associated with the completion of an I/O request.


## -syntax


````
ULONG_PTR GetInformation();
````


## -parameters






## -returns



<b>GetInformation</b> returns information (for example, the number of bytes transferred) that is associated with the completion of the I/O request.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRequestCompletionParams::GetInformation method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

