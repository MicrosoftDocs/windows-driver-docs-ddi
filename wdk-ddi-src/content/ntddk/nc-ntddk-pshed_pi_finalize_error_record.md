---
UID: NC:ntddk.PSHED_PI_FINALIZE_ERROR_RECORD
title: PSHED_PI_FINALIZE_ERROR_RECORD (ntddk.h)
description: A PSHED plug-in's FinalizeErrorRecord callback function adds supplementary error record sections to an error record that more fully describe the error condition.
old-location: whea\finalizeerrorrecord.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["PSHED_PI_FINALIZE_ERROR_RECORD callback function"]
ms.keywords: FinalizeErrorRecord, FinalizeErrorRecord callback function [WHEA Drivers and Applications], PSHED_PI_FINALIZE_ERROR_RECORD, PSHED_PI_FINALIZE_ERROR_RECORD callback, ntddk/FinalizeErrorRecord, whea.finalizeerrorrecord, whearef_fac1a23e-6b56-4b04-8930-e5f12f5c84a8.xml
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
req.irql: <= HIGH_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PSHED_PI_FINALIZE_ERROR_RECORD
 - ntddk/PSHED_PI_FINALIZE_ERROR_RECORD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_FINALIZE_ERROR_RECORD
---

# PSHED_PI_FINALIZE_ERROR_RECORD callback function


## -description

A PSHED plug-in's <i>FinalizeErrorRecord</i> callback function adds supplementary error record sections to an error record that more fully describe the error condition.

## -parameters

### -param PluginContext 

[in, out, optional]
A pointer to the context area that was specified in the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.

### -param ErrorSource 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that reported the hardware error.

### -param BufferLength 

[in]
The size, in bytes, of the buffer pointed to by the <i>ErrorRecord</i> parameter.

### -param ErrorRecord 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure that describes the error record that is being updated with supplementary error record sections.

## -returns

A PSHED plug-in's <i>FinalizeErrorRecord</i> callback function returns one of the following NTSTATUS codes:

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
The error record was successfully updated with any supplementary error record sections.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer pointed to by the <i>ErrorRecord </i>parameter as specified by the <i>BufferLength </i>parameter is too small to contain the error record if it is updated with the supplementary error record sections.

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

A PSHED plug-in that participates in error information retrieval sets the <b>Callbacks.RetrieveErrorInfo</b>, <b>Callbacks.FinalizeErrorRecord</b>, and <b>Callbacks.ClearErrorStatus</b> members of the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_retrieve_error_info">RetrieveErrorInfo</a>, <i>FinalizeErrorRecord</i>, and <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_status">ClearErrorStatus</a> callback functions when the plug-in calls the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInfoRetrieval</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED so that it can add supplementary error record sections to an error record. If a PSHED plug-in is registered to participate in error information retrieval, the PSHED calls the PSHED plug-in's <i>FinalizeErrorRecord</i> callback function so that the PSHED plug-in can add any additional error record sections to the error record that more fully describe the error condition.

A PSHED plug-in must ensure that it does not add supplementary error record sections beyond the end of the error record. The amount of memory that the Windows kernel allocates for a buffer to contain a particular error record is calculated from the <b>MaxRawDataLength</b> and <b>MaxSectionsPerRecord</b> members of the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that reported the hardware error. If a PSHED plug-in requires additional buffer space to contain the supplementary error record sections that it adds to the error record, it must participate in error source discovery and increase the value in the <b>MaxSectionsPerRecord</b> member of the <b>WHEA_ERROR_SOURCE_DESCRIPTOR</b> structure for each error source as appropriate to account for any supplementary error record sections.

The PSHED calls a PSHED plug-in's <i>FinalizeErrorRecord</i> callback function at IRQL <= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_status">ClearErrorStatus</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_retrieve_error_info">RetrieveErrorInfo</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>

