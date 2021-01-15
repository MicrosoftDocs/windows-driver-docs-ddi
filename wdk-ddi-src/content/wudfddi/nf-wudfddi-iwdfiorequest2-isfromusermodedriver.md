---
UID: NF:wudfddi.IWDFIoRequest2.IsFromUserModeDriver
title: IWDFIoRequest2::IsFromUserModeDriver (wudfddi.h)
description: The IsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application.
old-location: wdf\iwdfiorequest2_isfromusermodedriver.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::IsFromUserModeDriver"]
ms.keywords: IWDFIoRequest2 interface,IsFromUserModeDriver method, IWDFIoRequest2.IsFromUserModeDriver, IWDFIoRequest2::IsFromUserModeDriver, IsFromUserModeDriver, IsFromUserModeDriver method, IsFromUserModeDriver method,IWDFIoRequest2 interface, UMDFRequestObjectRef_81f13df9-e0f7-4d16-9f85-e049a491e08d.xml, umdf.iwdfiorequest2_isfromusermodedriver, wdf.iwdfiorequest2_isfromusermodedriver, wudfddi/IWDFIoRequest2::IsFromUserModeDriver
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest2::IsFromUserModeDriver
 - wudfddi/IWDFIoRequest2::IsFromUserModeDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest2::IsFromUserModeDriver
---

# IWDFIoRequest2::IsFromUserModeDriver


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsFromUserModeDriver</b> method indicates whether an I/O request came from a user-mode driver or an application.

## -returns

A Boolean value that, if <b>TRUE</b>, indicates that the current I/O request is from a user-mode driver. If this value is <b>FALSE</b>, the current I/O request came from an application.

## -remarks

If your driver supports <a href="/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">kernel-mode clients</a>, it should call <b>IsFromUserModeDriver</b> only if <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getrequestormode">IWDFIoRequest2::GetRequestorMode</a> returns <b>WdfUserMode</b>.

The UMDF 2 equivalent of this method is <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestisfromusermodedriver">WdfRequestIsFromUserModeDriver</a>.


#### Examples

For a code example that uses <b>IsFromUserModeDriver</b>, see the example at <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getrequestormode">IWDFIoRequest2::GetRequestorMode</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getrequestormode">IWDFIoRequest2::GetRequestorMode</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestisfromusermodedriver">WdfRequestIsFromUserModeDriver</a>

