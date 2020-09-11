---
UID: NF:wudfddi.IWDFIoRequest2.GetRequestorMode
title: IWDFIoRequest2::GetRequestorMode (wudfddi.h)
description: The GetRequestorMode method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).
old-location: wdf\iwdfiorequest2_getrequestormode.htm
tech.root: wdf
ms.assetid: 8f918bc4-d2d0-4d5b-93c8-89f02c81a701
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::GetRequestorMode"]
ms.keywords: GetRequestorMode, GetRequestorMode method, GetRequestorMode method,IWDFIoRequest2 interface, IWDFIoRequest2 interface,GetRequestorMode method, IWDFIoRequest2.GetRequestorMode, IWDFIoRequest2::GetRequestorMode, UMDFRequestObjectRef_ab2c358c-de7c-4bc3-b0cf-a598a1c69bd1.xml, umdf.iwdfiorequest2_getrequestormode, wdf.iwdfiorequest2_getrequestormode, wudfddi/IWDFIoRequest2::GetRequestorMode
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
 - IWDFIoRequest2::GetRequestorMode
 - wudfddi/IWDFIoRequest2::GetRequestorMode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest2.GetRequestorMode
---

# IWDFIoRequest2::GetRequestorMode


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetRequestorMode</b> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).

## -returns

<b>GetRequestorMode</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_kprocessor_mode">WDF_KPROCESSOR_MODE</a>-typed value that indicates whether the current I/O request came from a kernel-mode driver or a user-mode component.

## -remarks

A UMDF-based driver can receive an I/O request from a kernel-mode driver only if the UMDF-based driver supports <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">kernel-mode clients</a>. 

If <b>GetRequestorMode</b> returns <b>WdfUserMode</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-isfromusermodedriver">IWDFIoRequest2::IsFromUserModeDriver</a> to determine if the I/O request came from an application or a user-mode driver.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">IQueueCallbackWrite::OnWrite</a> callback function can determine whether an I/O request is from kernel mode or user mode. If the request is from user mode, the example determines whether the request is from an application or another user-mode driver.


```
VOID
STDMETHODCALLTYPE
  CMyQueue::OnWrite(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in SIZE_T BytesToWrite
    )
{
 WDF_KPROCESSOR_MODE processorMode;
    BOOL fromApp = FALSE;
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr<IWDFIoRequest2> r2 = pWdfRequest;

    processorMode = r2->GetRequestorMode();
    if (processorMode == WdfUserMode)
    {
        fromApp = r2->IsFromUserModeDriver();
    }
...
}
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-isfromusermodedriver">IWDFIoRequest2::IsFromUserModeDriver</a>

