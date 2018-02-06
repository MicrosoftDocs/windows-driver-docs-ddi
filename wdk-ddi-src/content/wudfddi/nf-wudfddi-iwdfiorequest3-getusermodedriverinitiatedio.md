---
UID: NF:wudfddi.IWDFIoRequest3.GetUserModeDriverInitiatedIo
title: IWDFIoRequest3::GetUserModeDriverInitiatedIo method
author: windows-driver-content
description: The GetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver.
old-location: wdf\iwdfiorequest3_getusermodedriverinitiatedio.htm
old-project: wdf
ms.assetid: 41C4E9D2-DC1B-4DFC-8C15-E9C21515B5F0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoRequest3, GetUserModeDriverInitiatedIo, IWDFIoRequest3::GetUserModeDriverInitiatedIo, wudfddi/IWDFIoRequest3::GetUserModeDriverInitiatedIo, GetUserModeDriverInitiatedIo method, IWDFIoRequest3 interface, GetUserModeDriverInitiatedIo method, GetUserModeDriverInitiatedIo method, IWDFIoRequest3 interface, wdf.iwdfiorequest3_getusermodedriverinitiatedio, umdf.iwdfiorequest3_getusermodedriverinitiatedio
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFIoRequest3.GetUserModeDriverInitiatedIo
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequest3::GetUserModeDriverInitiatedIo method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>GetUserModeDriverInitiatedIo</b> method determines whether an I/O request is marked as initiated by a UMDF driver.


## -syntax


````
BOOL GetUserModeDriverInitiatedIo();
````


## -parameters





## -returns


The method returns <b>TRUE</b> if the request is marked as UMDF driver-initiated and <b>FALSE</b> if the request is not marked as UMDF driver-initiated.



## -remarks


For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>.

The UMDF 2 equivalent of this method is <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetusermodedriverinitiatedio.md">WdfRequestGetUserModeInitiatedIo</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest3.md">IWDFIoRequest3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest3::GetUserModeDriverInitiatedIo method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

