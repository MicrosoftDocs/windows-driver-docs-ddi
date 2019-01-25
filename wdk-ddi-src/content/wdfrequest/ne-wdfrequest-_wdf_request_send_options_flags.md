---
UID: NE:wdfrequest._WDF_REQUEST_SEND_OPTIONS_FLAGS
title: "_WDF_REQUEST_SEND_OPTIONS_FLAGS" (wdfrequest.h)
description: The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_flags.htm
tech.root: wdf
ms.assetid: 68be1034-62f0-4444-b4c9-097277a7561f
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_0344916f-2437-4c32-9e05-c8204ac4f925.xml, WDF_REQUEST_SEND_OPTIONS_FLAGS, WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration, WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, WDF_REQUEST_SEND_OPTION_TIMEOUT, _WDF_REQUEST_SEND_OPTIONS_FLAGS, kmdf.wdf_request_send_options_flags, wdf.wdf_request_send_options_flags, wdfrequest/WDF_REQUEST_SEND_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE, wdfrequest/WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT, wdfrequest/WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE, wdfrequest/WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET, wdfrequest/WDF_REQUEST_SEND_OPTION_SYNCHRONOUS, wdfrequest/WDF_REQUEST_SEND_OPTION_TIMEOUT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
-	WDF_REQUEST_SEND_OPTIONS_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS_FLAGS
---

# _WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_SEND_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -enum-fields




### -field WDF_REQUEST_SEND_OPTION_TIMEOUT

If the driver sets this flag, the <b>Timeout</b> member of the WDF_REQUEST_SEND_OPTIONS structure is valid.


### -field WDF_REQUEST_SEND_OPTION_SYNCHRONOUS

If the driver sets this flag, the framework handles the associated I/O request synchronously. (The driver does not have to set this flag if it is calling an object method whose name ends with "Synchronously", such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff548669">WdfIoTargetSendReadSynchronously</a>.)


### -field WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE

If the driver sets this flag, the framework sends the I/O request to the I/O target, regardless of the I/O target's state. If not set, the framework queues the request if the target is stopped. Setting this flag allows a driver to send a request, such as a request to reset a USB pipe, to a device after the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a>.


### -field WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET

If the driver sets this flag, the driver is sending the request asynchronously and does not need to be notified when the request is completed or canceled. The framework sends the I/O request to the I/O target, regardless of the I/O target's state. The driver does not set a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function or call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> for the request. If the driver sets this flag, it cannot set any other flags. For more information about this flag, see the following Remarks section.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT

This flag applies to UMDF only. If set, and if the I/O request type is <b>WdfRequestTypeCreate</b>, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> method attempts to pass the client's impersonation level to the driver's I/O target. The <b>WdfRequestSend</b> method returns an error code if the impersonation attempt fails, unless the driver also sets the <b>WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE</b> flag.


### -field WDF_REQUEST_SEND_OPTION_IMPERSONATION_IGNORE_FAILURE

This flag applies to UMDF only. If set, the framework still sends the request even if impersonation fails.  You can use this value only with <b>WDF_REQUEST_SEND_OPTION_IMPERSONATE_CLIENT</b>.


## -remarks



A driver that sets the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag typically does not format the I/O request before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request to an I/O target. In fact, a driver that sets this flag must not call any of the <b>WdfIoTargetFormatRequestFor</b><i>Xxx</i> methods before it calls <b>WdfRequestSend</b>. The driver can use only the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549955">WdfRequestFormatRequestUsingCurrentType</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550036">WdfRequestWdmFormatUsingStackLocation</a> method to format the request.

Your driver <i>cannot</i> set the WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET flag in the following situations:

<ul>
<li>
The driver created the request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a>.

</li>
<li>
The driver is sending the I/O request to a remote I/O target and the driver specified the <a href="https://msdn.microsoft.com/27aa5d78-03ce-4fc9-b1c8-d02a760e2787">WdfIoTargetOpenByName</a> flag when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>.

</li>
<li>
The driver is sending the I/O request to a remote I/O target, and the driver specified both the <a href="https://msdn.microsoft.com/27aa5d78-03ce-4fc9-b1c8-d02a760e2787">WdfIoTargetOpenUseExistingDevice</a> flag and a <a href="https://msdn.microsoft.com/9539868c-127b-4781-9a73-b56fbfda3233">TargetFileObject</a> pointer when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>.

</li>
<li>
The request type is <a href="https://msdn.microsoft.com/91c036a0-7fce-4c7d-a217-eb1c487a15d0">WdfRequestTypeCreate</a> and the driver has not set the <a href="https://msdn.microsoft.com/e0887061-eafe-4dba-bb7a-58bf949e2d08">WdfFileObjectNotRequired</a> flag. (For more information about this situation, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.)

</li>
</ul>
For the UMDF version of this enumeration, see <a href="https://msdn.microsoft.com/library/windows/hardware/Ff552493">WDF_REQUEST_SEND_OPTIONS_FLAGS (UMDF)</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a>
 

 

