---
UID: NC:ntddk.PSHED_PI_DISABLE_ERROR_SOURCE
title: PSHED_PI_DISABLE_ERROR_SOURCE (ntddk.h)
description: A PSHED plug-in's DisableErrorSource callback function disables an error source.
old-location: whea\disableerrorsource.htm
tech.root: whea
ms.assetid: 062927db-9581-447a-820b-82687710ea8d
ms.date: 02/20/2018
keywords: ["PSHED_PI_DISABLE_ERROR_SOURCE callback function"]
ms.keywords: DisableErrorSource, DisableErrorSource callback function [WHEA Drivers and Applications], PSHED_PI_DISABLE_ERROR_SOURCE, PSHED_PI_DISABLE_ERROR_SOURCE callback, ntddk/DisableErrorSource, whea.disableerrorsource, whearef_41df46d2-6f6e-47aa-8296-cdc9223a9f26.xml
f1_keywords:
 - "ntddk/DisableErrorSource"
 - "DisableErrorSource"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- DisableErrorSource
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_DISABLE_ERROR_SOURCE callback function


## -description


A PSHED plug-in's <i>DisableErrorSource</i> callback function disables an error source.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that is being disabled.


## -returns



A PSHED plug-in's <i>DisableErrorSource</i> callback function returns one of the following NTSTATUS codes:

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
The error source was successfully disabled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The PSHED plug-in does not support disabling the specified error source.

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



A PSHED plug-in that participates in error source control sets the <b>Callbacks.SetErrorSourceInfo</b>, <b>Callbacks.EnableErrorSource</b>, and <b>Callbacks.DisableErrorSource</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_set_error_source_info">SetErrorSourceInfo</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_enable_error_source">EnableErrorSource</a>, and <i>DisableErrorSource</i> callback functions when the plug-in calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorSourceControl</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to disable an error source in response to an error source disable request by a WHEA management application. If a PSHED plug-in is registered to participate in error source control, the PSHED calls the PSHED plug-in's <i>DisableErrorSource</i> callback function to give the PSHED plug-in an opportunity to disable the error source. If the <i>DisableErrorSource</i> callback function returns STATUS_NOT_SUPPORTED, the PSHED will disable the error source. Otherwise, the PSHED will just return the return value that is returned by the <i>DisableErrorSource</i> callback function.

If the PSHED plug-in successfully disables the error source, the PSHED will update the WHEA_ERROR_SOURCE_DESCRIPTOR structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's <i>DisableErrorSource</i> callback function returns. A PSHED plug-in's <i>DisableErrorSource</i> callback function should not modify the error source descriptor.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_enable_error_source">EnableErrorSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_set_error_source_info">SetErrorSourceInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

