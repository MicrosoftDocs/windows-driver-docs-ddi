---
UID: NE:wdfrequest._WDF_REQUEST_SEND_OPTIONS_FLAGS
title: "_WDF_REQUEST_SEND_OPTIONS_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_flags.htm
old-project: wdf
ms.assetid: 68be1034-62f0-4444-b4c9-097277a7561f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfrequest/WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, WDF_REQUEST_SEND_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, wdf.wdf_request_send_options_flags, DFRequestObjectRef_0344916f-2437-4c32-9e05-c8204ac4f925.xml, WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration, wdfrequest/WDF_REQUEST_SEND_OPTION_TIMEOUT, _WDF_REQUEST_SEND_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, kmdf.wdf_request_send_options_flags, wdfrequest/WDF_REQUEST_SEND_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, wdfrequest/WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, WDF_REQUEST_SEND_OPTION_TIMEOUT, WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_SEND_OPTIONS_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_SEND_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -syntax


````
typedef enum _WDF_REQUEST_SEND_OPTIONS_FLAGS { 
  WDF_REQUEST_SEND_OPTION_TIMEOUT                       = 0x0000001,
  WDF_REQUEST_SEND_OPTION_SYNCHRONOUS                   = 0x0000002,
  WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE           = 0x0000004,
  WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET               = 0x0000008,
  WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT            = 0x00010000,
  WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE  = 0x00020000
} WDF_REQUEST_SEND_OPTIONS_FLAGS;
````


## -enum-fields




### -field WDF_REQUEST_SEND_OPTION_TIMEOUT

If the driver sets this flag, the <b>Timeout</b> member of the WDF_REQUEST_SEND_OPTIONS structure is valid.


### -field WDF_REQUEST_SEND_OPTION_SYNCHRONOUS

If the driver sets this flag, the framework handles the associated I/O request synchronously. (The driver does not have to set this flag if it is calling an object method whose name ends with "Synchronously", such as <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendreadsynchronously.md">WdfIoTargetSendReadSynchronously</a>.)


### -field WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE

If the driver sets this flag, the framework sends the I/O request to the I/O target, regardless of the I/O target's state. If not set, the framework queues the request if the target is stopped. Setting this flag allows a driver to send a request, such as a request to reset a USB pipe, to a device after the driver has called <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a>.


### -field WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET

If the driver sets this flag, the driver is sending the request asynchronously and does not need to be notified when the request is completed or canceled. The framework sends the I/O request to the I/O target, regardless of the I/O target's state. The driver does not set a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function or call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> for the request. If the driver sets this flag, it cannot set any other flags. For more information about this flag, see the following Remarks section.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT

This flag applies to UMDF only. If set, and if the I/O request type is <b>WdfRequestTypeCreate</b>, the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> method attempts to pass the client's impersonation level to the driver's I/O target. The <b>WdfRequestSend</b> method returns an error code if the impersonation attempt fails, unless the driver also sets the <b>WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE</b> flag.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE

This flag applies to UMDF only. If set, the framework still sends the request even if impersonation fails.  You can use this value only with <b>WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT</b>.


## -remarks


A driver that sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag typically does not format the I/O request before it calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request to an I/O target. In fact, a driver that sets this flag must not call any of the <b>WdfIoTargetFormatRequestFor</b><i>Xxx</i> methods before it calls <b>WdfRequestSend</b>. The driver can use only the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestformatrequestusingcurrenttype.md">WdfRequestFormatRequestUsingCurrentType</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestwdmformatusingstacklocation.md">WdfRequestWdmFormatUsingStackLocation</a> method to format the request.

Your driver <i>cannot</i> set the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag in the following situations:
<ul>
<li>
The driver created the request object by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>.

</li>
<li>
The driver is sending the I/O request to a remote I/O target and the driver specified the <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WdfIoTargetOpenByName</a> flag when it called <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>.

</li>
<li>
The driver is sending the I/O request to a remote I/O target, and the driver specified both the <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WdfIoTargetOpenUseExistingDevice</a> flag and a <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">TargetFileObject</a> pointer when it called <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>.

</li>
<li>
The request type is <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WdfRequestTypeCreate</a> and the driver has not set the <a href="..\wdfdevice\ne-wdfdevice-_wdf_fileobject_class.md">WdfFileObjectNotRequired</a> flag. (For more information about this situation, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.)

</li>
</ul>For the UMDF version of this enumeration, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_send_options_flags.md">WDF_REQUEST_SEND_OPTIONS_FLAGS (UMDF)</a>.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

