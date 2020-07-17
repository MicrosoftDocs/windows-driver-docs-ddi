---
UID: NE:wdfrequest._WDF_REQUEST_SEND_OPTIONS_FLAGS
title: _WDF_REQUEST_SEND_OPTIONS_FLAGS (wdfrequest.h)
description: The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_flags.htm
tech.root: wdf
ms.assetid: 68be1034-62f0-4444-b4c9-097277a7561f
ms.date: 02/26/2018
keywords: ["_WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration"]
ms.keywords: DFRequestObjectRef_0344916f-2437-4c32-9e05-c8204ac4f925.xml, WDF_REQUEST_SEND_OPTIONS_FLAGS, WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration, WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, WDF_REQUEST_SEND_OPTION_TIMEOUT, _WDF_REQUEST_SEND_OPTIONS_FLAGS, kmdf.wdf_request_send_options_flags, wdf.wdf_request_send_options_flags, wdfrequest/WDF_REQUEST_SEND_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, wdfrequest/WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, wdfrequest/WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, wdfrequest/WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, wdfrequest/WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, wdfrequest/WDF_REQUEST_SEND_OPTION_TIMEOUT
f1_keywords:
 - "wdfrequest/WDF_REQUEST_SEND_OPTIONS_FLAGS"
 - "WDF_REQUEST_SEND_OPTIONS_FLAGS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfrequest.h
api_name:
- WDF_REQUEST_SEND_OPTIONS_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS_FLAGS
---

# _WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_SEND_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -enum-fields




### -field WDF_REQUEST_SEND_OPTION_TIMEOUT

If the driver sets this flag, the <b>Timeout</b> member of the WDF_REQUEST_SEND_OPTIONS structure is valid.


### -field WDF_REQUEST_SEND_OPTION_SYNCHRONOUS

If the driver sets this flag, the framework handles the associated I/O request synchronously. (The driver does not have to set this flag if it is calling an object method whose name ends with "Synchronously", such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendreadsynchronously">WdfIoTargetSendReadSynchronously</a>.)


### -field WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE

If the driver sets this flag, the framework sends the I/O request to the I/O target, regardless of the I/O target's state. If not set, the framework queues the request if the target is stopped. Setting this flag allows a driver to send a request, such as a request to reset a USB pipe, to a device after the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a>.


### -field WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET

If the driver sets this flag, the driver is sending the request asynchronously and does not need to be notified when the request is completed or canceled. The framework sends the I/O request to the I/O target, regardless of the I/O target's state. The driver does not set a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function or call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> for the request. If the driver sets this flag, it cannot set any other flags. For more information about this flag, see the following Remarks section.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT

This flag applies to UMDF only. If set, and if the I/O request type is <b>WdfRequestTypeCreate</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> method attempts to pass the client's impersonation level to the driver's I/O target. The <b>WdfRequestSend</b> method returns an error code if the impersonation attempt fails, unless the driver also sets the <b>WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE</b> flag.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE

This flag applies to UMDF only. If set, the framework still sends the request even if impersonation fails.  You can use this value only with <b>WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT</b>.


## -remarks



A driver that sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag typically does not format the I/O request before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> to send the request to an I/O target. In fact, a driver that sets this flag must not call any of the <b>WdfIoTargetFormatRequestFor</b><i>Xxx</i> methods before it calls <b>WdfRequestSend</b>. The driver can use only the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestformatrequestusingcurrenttype">WdfRequestFormatRequestUsingCurrentType</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestwdmformatusingstacklocation">WdfRequestWdmFormatUsingStackLocation</a> method to format the request.

Your driver <i>cannot</i> set the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag in the following situations:

<ul>
<li>
The driver created the request object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>.

</li>
<li>
The driver is sending the I/O request to a remote I/O target and the driver specified the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WdfIoTargetOpenByName</a> flag when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>.

</li>
<li>
The driver is sending the I/O request to a remote I/O target, and the driver specified both the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WdfIoTargetOpenUseExistingDevice</a> flag and a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">TargetFileObject</a> pointer when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>.

</li>
<li>
The request type is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WdfRequestTypeCreate</a> and the driver has not set the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WdfFileObjectNotRequired</a> flag. (For more information about this situation, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.)

</li>
</ul>
For the UMDF version of this enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTIONS_FLAGS (UMDF)</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a>
 

 

