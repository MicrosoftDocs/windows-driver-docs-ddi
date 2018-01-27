---
UID: NF:wudfddi.IWDFIoRequest.IsFrom32BitProcess
title: IWDFIoRequest::IsFrom32BitProcess method
author: windows-driver-content
description: The IsFrom32BitProcess method determines whether a request originated from a 32-bit process.
old-location: wdf\iwdfiorequest_isfrom32bitprocess.htm
old-project: wdf
ms.assetid: 80e43bd7-9ab9-46b0-a7f3-08c3577be4bc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IsFrom32BitProcess method, IWDFIoRequest interface, IWDFIoRequest::IsFrom32BitProcess, IWDFIoRequest, umdf.iwdfiorequest_isfrom32bitprocess, UMDFRequestObjectRef_728bc611-2c40-4a49-b967-77e388072860.xml, wdf.iwdfiorequest_isfrom32bitprocess, IsFrom32BitProcess method, IWDFIoRequest interface, IsFrom32BitProcess method, IsFrom32BitProcess, wudfddi/IWDFIoRequest::IsFrom32BitProcess
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
-	IWDFIoRequest.IsFrom32BitProcess
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::IsFrom32BitProcess method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsFrom32BitProcess</b> method determines whether a request originated from a 32-bit process.


## -syntax


````
BOOL  IsFrom32BitProcess();
````


## -parameters





## -returns


<b>IsFrom32BitProcess</b> returns a BOOL value that indicates whether the request originated from a 32-bit process. <b>TRUE</b> indicates the request originated from a 32-bit process. <b>FALSE</b> indicates the request did not originate from a 32-bit process.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::IsFrom32BitProcess method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

