---
UID: NC:ntddk.PSHED_PI_RETRIEVE_ERROR_INFO
title: PSHED_PI_RETRIEVE_ERROR_INFO
author: windows-driver-content
description: A PSHED plug-in's RetrieveErrorInfo callback function retrieves platform-specific error information about a hardware error that has occurred.
old-location: whea\retrieveerrorinfo.htm
old-project: whea
ms.assetid: 4d299057-a1cc-4b53-8ab4-031672181e74
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PSHED_PI_RETRIEVE_ERROR_INFO, RetrieveErrorInfo, RetrieveErrorInfo callback function [WHEA Drivers and Applications], ntddk/RetrieveErrorInfo, whea.retrieveerrorinfo, whearef_f231db3f-6108-4229-895f-7e0281b5b3b8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: "<= HIGH_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	RetrieveErrorInfo
product: Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---

# PSHED_PI_RETRIEVE_ERROR_INFO callback


## -description


A PSHED plug-in's <i>RetrieveErrorInfo</i> callback function retrieves platform-specific error information about a hardware error that has occurred.


## -prototype


````
PSHED_PI_RETRIEVE_ERROR_INFO RetrieveErrorInfo;

NTSTATUS RetrieveErrorInfo(
  _Inout_opt_ PVOID                         PluginContext,
  _In_        PWHEA_ERROR_SOURCE_DESCRIPTOR ErrorSource,
  _In_        ULONGLONG                     BufferLength,
  _Inout_     PWHEA_ERROR_PACKET            Packet
)
{ ... }
````


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in]

A pointer to a <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that reported the hardware error.


### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by the <i>Packet</i> parameter.


### -param Packet [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure that describes the hardware error packet for the hardware error.


## -returns



A PSHED plug-in's <i>RetrieveErrorInfo</i> callback function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The hardware error packet was successfully updated with any platform-specific error information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer pointed to by the <i>Packet </i>parameter as specified by the <i>BufferLength </i>parameter is too small to contain the hardware error packet if it is updated with the platform-specific error information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The PSHED plug-in does not support the specified error source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A PSHED plug-in that participates in error information retrieval sets the <b>Callbacks.RetrieveErrorInfo</b>, <b>Callbacks.FinalizeErrorRecord</b>, and <b>Callbacks.ClearErrorStatus</b> members of the <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>RetrieveErrorInfo</i>, <a href="..\ntddk\nc-ntddk-pshed_pi_finalize_error_record.md">FinalizeErrorRecord</a>, and <a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md">ClearErrorStatus</a> callback functions when the plug-in calls the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInfoRetrieval</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

Each low-level hardware error handler (LLHEH) calls into the PSHED to retrieve any platform-specific error information about a hardware error that has occurred. If a PSHED plug-in is registered to participate in error information retrieval, the PSHED calls the PSHED plug-in's <i>RetrieveErrorInfo</i> callback function so that it can update the hardware error packet with any platform-specific error information. The PSHED plug-in can modify the existing contents of the hardware error packet as well as add supplementary information to the hardware error packet. Supplementary information is added to a hardware error packet beginning at the offset specified by the <b>RawDataOffset</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure.

A PSHED plug-in must ensure that it does not add supplementary information beyond the end of the hardware error packet. The amount of memory that an LLHEH allocates for a buffer to contain a particular hardware error packet is calculated from the <b>MaxRawDataLength</b> member of the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source. If a PSHED plug-in requires additional buffer space to contain the supplementary information, it must participate in error source discovery and increase the value in the <b>MaxRawDataLength</b> member of the <b>WHEA_ERROR_SOURCE_DESCRIPTOR</b> structure for each error source as appropriate to account for any supplemental information.

For most error sources, the PSHED plug-in's <i>RetrieveErrorInfo</i> callback function is called at a high IRQL. In such a situation, the PSHED plug-in's <i>RetrieveErrorInfo</i> callback function must only perform operations and make calls to other functions that are permitted at a high IRQL.

An important task of a PSHED plug-in's <i>RetrieveErrorInfo</i> callback function is to ensure that the severity of the error condition as specified by the <b>ErrorSeverity</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> is appropriate. For example, if the severity level of the error condition is reported as <b>WheaErrSevFatal </b>by the LLHEH but the PSHED plug-in supports a recovery mechanism for the particular error condition that was reported, the PSHED plug-in can change the severity level to <b>WheaErrSevRecoverable </b>so that the operating system will attempt recovery from the error. Similarly, if the severity level of the error condition is reported as <b>WheaErrSevRecoverable </b>by the LLHEH but the PSHED plug-in recognizes that attempting recovery of the particular error condition that was reported would only cause further problems, the PSHED plug-in can change the severity level to <b>WheaErrSevFatal </b>so that the operating system will not attempt recovery from the error.

<div class="alert"><b>Important</b>    For corrected hardware errors, a PSHED plug-in must retrieve all of the error status information that it requires for processing the error condition from within its <i>RetrieveErrorInfo</i> callback function, as the remainder of the processing of the hardware error is not guaranteed to be synchronized with the LLHEH.</div>
<div> </div>
The PSHED calls a PSHED plug-in's <i>RetrieveErrorInfo</i> callback function at IRQL &lt;= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="..\ntddk\nc-ntddk-pshed_pi_finalize_error_record.md">FinalizeErrorRecord</a>



<a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>



<a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md">ClearErrorStatus</a>



<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_RETRIEVE_ERROR_INFO callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

