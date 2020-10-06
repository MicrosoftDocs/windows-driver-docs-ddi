---
UID: NF:wudfddi.IImpersonateCallback.OnImpersonate
title: IImpersonateCallback::OnImpersonate (wudfddi.h)
description: The OnImpersonate method handles impersonation.
old-location: wdf\iimpersonatecallback_onimpersonate.htm
tech.root: wdf
ms.assetid: 6f06e89c-5298-4335-ab9a-ef69e635152c
ms.date: 02/26/2018
keywords: ["IImpersonateCallback::OnImpersonate"]
ms.keywords: IImpersonateCallback interface,OnImpersonate method, IImpersonateCallback.OnImpersonate, IImpersonateCallback::OnImpersonate, OnImpersonate, OnImpersonate method, OnImpersonate method,IImpersonateCallback interface, UMDFRequestObjectRef_e3752371-61b0-44ba-af86-0cf244e27894.xml, umdf.iimpersonatecallback_onimpersonate, wdf.iimpersonatecallback_onimpersonate, wudfddi/IImpersonateCallback::OnImpersonate
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IImpersonateCallback::OnImpersonate
 - wudfddi/IImpersonateCallback::OnImpersonate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IImpersonateCallback.OnImpersonate
---

# IImpersonateCallback::OnImpersonate


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnImpersonate</b> method handles impersonation.

## -parameters

### -param Context 

[in, optional]
A pointer to a context that was previously supplied in the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-impersonate">IWDFIoRequest::Impersonate</a> method. This parameter is optional and can be <b>NULL</b> if a context is not required.

## -remarks

Typically, the driver uses this callback to call a Win32 function directly. For example, if the driver must open a data file on behalf of an application that sent an I/O operation, the driver requires impersonation only to open the file handle.

To ensure that impersonation does not leak across driver callback functions or between device drivers, <b>OnImpersonate</b> should not call any framework methods.

A driver registers the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iimpersonatecallback">IImpersonateCallback</a> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-impersonate">IWDFIoRequest::Impersonate</a> method. 

For more information about how UMDF and UMDF drivers handle impersonation, see <a href="/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Impersonation</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iimpersonatecallback">IImpersonateCallback</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-impersonate">IWDFIoRequest::Impersonate</a>