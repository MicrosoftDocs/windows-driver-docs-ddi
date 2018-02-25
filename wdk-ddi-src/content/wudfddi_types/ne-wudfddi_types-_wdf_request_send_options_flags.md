---
UID: NE:wudfddi_types._WDF_REQUEST_SEND_OPTIONS_FLAGS
title: "_WDF_REQUEST_SEND_OPTIONS_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that a driver can specify when it calls IWDFIoRequest::Send.
old-location: wdf\wdf_request_send_options_flags__umdf_.htm
old-project: wdf
ms.assetid: 02678466-aa8d-436d-8be3-b8a57218a106
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, A, D, E, F, G, I, L, N, O, P, Q, R, S, T, U, W, WDF_REQUEST_SEND_OPTIONS_FLAGS, WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration, WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, WDF_REQUEST_SEND_OPTION_TIMEOUT, _, _WDF_REQUEST_SEND_OPTIONS_FLAGS, umdf.wdf_request_send_options_flags__umdf_, umdfstructs_a99bff2d-2fa0-4267-b3be-aa9fd01a0778.xml, wdf.wdf_request_send_options_flags__umdf_, wudfddi_types/WDF_REQUEST_SEND_OPTIONS_FLAGS, wudfddi_types/WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, wudfddi_types/WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, wudfddi_types/WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, wudfddi_types/WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, wudfddi_types/WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, wudfddi_types/WDF_REQUEST_SEND_OPTION_TIMEOUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_types.h
apiname:
-	WDF_REQUEST_SEND_OPTIONS_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>WDF_REQUEST_SEND_OPTIONS_FLAGS</b> enumeration type defines flags that a driver can specify when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>.


## -syntax


````
typedef enum _WDF_REQUEST_SEND_OPTIONS_FLAGS { 
  WDF_REQUEST_SEND_OPTION_TIMEOUT                       = 0x00000001,
  WDF_REQUEST_SEND_OPTION_SYNCHRONOUS                   = 0x00000002,
  WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE           = 0x00000004,
  WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET               = 0x00000008,
  WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT            = 0x00010000,
  WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE  = 0x00020000
} WDF_REQUEST_SEND_OPTIONS_FLAGS;
````


## -enum-fields




### -field WDF_REQUEST_SEND_OPTION_TIMEOUT

If set, the <i>Timeout</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method is valid.


### -field WDF_REQUEST_SEND_OPTION_SYNCHRONOUS

If set, UMDF sends the I/O request synchronously.


### -field WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE

If set, UMDF sends the I/O request to the I/O target, regardless of the I/O target's state. If not set, UMDF queues the request if the target is stopped. Setting this flag allows a driver to send a request, such as a request to reset a USB pipe, to a device after the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a>. 


### -field WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET

If set, the driver is sending the request asynchronously and does not need to be notified when the request is completed or canceled. The driver does not set an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function or call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> for the request. For more information about this flag, see the following Remarks section. 


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT

If set, and if the I/O request type is <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WdfRequestCreate</a>, the <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a> method attempts to pass the client's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">impersonation</a> level to the driver's I/O target. This value is available in UMDF versions 1.9 and later.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE

If set, UMDF ignores impersonation failures. You can use this value only with WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT. This value is available in UMDF versions 1.9 and later.


## -remarks



A driver that sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag typically does not format the I/O request before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> to send the request to an I/O target. In fact, a driver that sets this flag must not call any of the <b>IWdfIoTarget::FormatRequestFor</b><i>Xxx</i> methods before it calls <b>IWDFIoRequest::Send</b>. The driver can use only the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559077">IWDFIoRequest::FormatUsingCurrentType</a> method to format the request.

Your driver cannot set the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag if the <i>pIoTarget</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> points to a file-handle-based I/O target object. For more information about this type of I/O target, see <a href="https://msdn.microsoft.com/cf1b39c3-4c82-411b-8eef-117ac0fe793e">Initializing a General I/O Target in UMDF</a>.

If the driver sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag, it cannot set any other flags except WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT and WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE.

For more information about client impersonation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Client Impersonation</a>.

For the KMDF version of this enumeration, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_send_options_flags.md">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

