---
UID: NF:wudfddi.IWDFIoRequest2.IsFromUserModeDriver
title: IWDFIoRequest2::IsFromUserModeDriver method
author: windows-driver-content
description: The IsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application.
old-location: wdf\iwdfiorequest2_isfromusermodedriver.htm
old-project: wdf
ms.assetid: 17a1e4d8-5438-42b6-b4a5-335e7bd57b1b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFIoRequest2, IWDFIoRequest2 interface, IsFromUserModeDriver method, IWDFIoRequest2::IsFromUserModeDriver, IsFromUserModeDriver method, IsFromUserModeDriver method, IWDFIoRequest2 interface, IsFromUserModeDriver,IWDFIoRequest2.IsFromUserModeDriver, UMDFRequestObjectRef_81f13df9-e0f7-4d16-9f85-e049a491e08d.xml, umdf.iwdfiorequest2_isfromusermodedriver, wdf.iwdfiorequest2_isfromusermodedriver, wudfddi/IWDFIoRequest2::IsFromUserModeDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFIoRequest2.IsFromUserModeDriver
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::IsFromUserModeDriver method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsFromUserModeDriver</b> method indicates whether an I/O request came from a user-mode driver or an application.


## -syntax


````
BOOL IsFromUserModeDriver();
````


## -parameters






## -returns



A Boolean value that, if <b>TRUE</b>, indicates that the current I/O request is from a user-mode driver. If this value is <b>FALSE</b>, the current I/O request came from an application.




## -remarks



If your driver supports <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">kernel-mode clients</a>, it should call <b>IsFromUserModeDriver</b> only if <a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a> returns <b>WdfUserMode</b>.

The UMDF 2 equivalent of this method is <a href="..\wdfrequest\nf-wdfrequest-wdfrequestisfromusermodedriver.md">WdfRequestIsFromUserModeDriver</a>.


#### Examples

For a code example that uses <b>IsFromUserModeDriver</b>, see the example at <a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestisfromusermodedriver.md">WdfRequestIsFromUserModeDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::IsFromUserModeDriver method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

