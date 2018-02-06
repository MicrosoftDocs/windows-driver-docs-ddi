---
UID: NF:wudfddi.IWDFIoRequest2.GetRequestorMode
title: IWDFIoRequest2::GetRequestorMode method
author: windows-driver-content
description: The GetRequestorMode method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).
old-location: wdf\iwdfiorequest2_getrequestormode.htm
old-project: wdf
ms.assetid: 8f918bc4-d2d0-4d5b-93c8-89f02c81a701
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: GetRequestorMode, wudfddi/IWDFIoRequest2::GetRequestorMode, IWDFIoRequest2 interface, GetRequestorMode method, GetRequestorMode method, IWDFIoRequest2 interface, GetRequestorMode method, IWDFIoRequest2::GetRequestorMode, IWDFIoRequest2, umdf.iwdfiorequest2_getrequestormode, wdf.iwdfiorequest2_getrequestormode, UMDFRequestObjectRef_ab2c358c-de7c-4bc3-b0cf-a598a1c69bd1.xml
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
-	IWDFIoRequest2.GetRequestorMode
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequest2::GetRequestorMode method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetRequestorMode</b> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).


## -syntax


````
WDF_KPROCESSOR_MODE GetRequestorMode();
````


## -parameters





## -returns


<b>GetRequestorMode</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_kprocessor_mode.md">WDF_KPROCESSOR_MODE</a>-typed value that indicates whether the current I/O request came from a kernel-mode driver or a user-mode component.



## -remarks


A UMDF-based driver can receive an I/O request from a kernel-mode driver only if the UMDF-based driver supports <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">kernel-mode clients</a>. 

If <b>GetRequestorMode</b> returns <b>WdfUserMode</b>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559021">IWDFIoRequest2::IsFromUserModeDriver</a> to determine if the I/O request came from an application or a user-mode driver.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559021">IWDFIoRequest2::IsFromUserModeDriver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::GetRequestorMode method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

