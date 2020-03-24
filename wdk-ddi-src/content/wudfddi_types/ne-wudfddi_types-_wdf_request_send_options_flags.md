---
UID: NE:wudfddi_types._WDF_REQUEST_SEND_OPTIONS_FLAGS
title: _WDF_REQUEST_SEND_OPTIONS_FLAGS (wudfddi_types.h)
description: The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that a driver can specify when it calls IWDFIoRequest::Send.
old-location: wdf\wdf_request_send_options_flags__umdf_.htm
tech.root: wdf
ms.assetid: 02678466-aa8d-436d-8be3-b8a57218a106
ms.date: 02/26/2018
keywords: ["_WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration"]
ms.keywords: WDF_REQUEST_SEND_OPTIONS_FLAGS, WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration, WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, WDF_REQUEST_SEND_OPTION_TIMEOUT, _WDF_REQUEST_SEND_OPTIONS_FLAGS, umdf.wdf_request_send_options_flags__umdf_, umdfstructs_a99bff2d-2fa0-4267-b3be-aa9fd01a0778.xml, wdf.wdf_request_send_options_flags__umdf_, wudfddi_types/WDF_REQUEST_SEND_OPTIONS_FLAGS, wudfddi_types/WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, wudfddi_types/WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, wudfddi_types/WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, wudfddi_types/WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, wudfddi_types/WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, wudfddi_types/WDF_REQUEST_SEND_OPTION_TIMEOUT
f1_keywords:
 - "wudfddi_types/WDF_REQUEST_SEND_OPTIONS_FLAGS"
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_types.h
api_name:
- WDF_REQUEST_SEND_OPTIONS_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS_FLAGS
---

# _WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>WDF_REQUEST_SEND_OPTIONS_FLAGS</b> enumeration type defines flags that a driver can specify when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>.


## -enum-fields




### -field WDF_REQUEST_SEND_OPTION_TIMEOUT

If set, the <i>Timeout</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a> method is valid.


### -field WDF_REQUEST_SEND_OPTION_SYNCHRONOUS

If set, UMDF sends the I/O request synchronously.


### -field WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE

If set, UMDF sends the I/O request to the I/O target, regardless of the I/O target's state. If not set, UMDF queues the request if the target is stopped. Setting this flag allows a driver to send a request, such as a request to reset a USB pipe, to a device after the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a>. 


### -field WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET

If set, the driver is sending the request asynchronously and does not need to be notified when the request is completed or canceled. The driver does not set an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">IRequestCallbackRequestCompletion::OnCompletion</a> callback function or call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> for the request. For more information about this flag, see the following Remarks section. 


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT

If set, and if the I/O request type is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">Send</a> method attempts to pass the client's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">impersonation</a> level to the driver's I/O target. This value is available in UMDF versions 1.9 and later.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE

If set, UMDF ignores impersonation failures. You can use this value only with WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT. This value is available in UMDF versions 1.9 and later.


## -remarks



A driver that sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag typically does not format the I/O request before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a> to send the request to an I/O target. In fact, a driver that sets this flag must not call any of the <b>IWdfIoTarget::FormatRequestFor</b><i>Xxx</i> methods before it calls <b>IWDFIoRequest::Send</b>. The driver can use only the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-formatusingcurrenttype">IWDFIoRequest::FormatUsingCurrentType</a> method to format the request.

Your driver cannot set the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag if the <i>pIoTarget</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a> points to a file-handle-based I/O target object. For more information about this type of I/O target, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/initializing-a-general-i-o-target-in-umdf">Initializing a General I/O Target in UMDF</a>.

If the driver sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag, it cannot set any other flags except WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT and WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE.

For more information about client impersonation, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Client Impersonation</a>.

For the KMDF version of this enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>
 

 

