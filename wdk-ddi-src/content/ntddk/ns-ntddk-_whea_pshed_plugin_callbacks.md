---
UID: NS:ntddk._WHEA_PSHED_PLUGIN_CALLBACKS
title: _WHEA_PSHED_PLUGIN_CALLBACKS (ntddk.h)
description: The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in.
old-location: whea\whea_pshed_plugin_callbacks.htm
tech.root: whea
ms.assetid: 3b99f2bf-0ebc-40b2-a586-acc89200132b
ms.date: 02/20/2018
ms.keywords: "*PWHEA_PSHED_PLUGIN_CALLBACKS, PWHEA_PSHED_PLUGIN_CALLBACKS, PWHEA_PSHED_PLUGIN_CALLBACKS structure pointer [WHEA Drivers and Applications], WHEA_PSHED_PLUGIN_CALLBACKS, WHEA_PSHED_PLUGIN_CALLBACKS structure [WHEA Drivers and Applications], _WHEA_PSHED_PLUGIN_CALLBACKS, ntddk/PWHEA_PSHED_PLUGIN_CALLBACKS, ntddk/WHEA_PSHED_PLUGIN_CALLBACKS, whea.whea_pshed_plugin_callbacks, whearef_85037502-834f-412c-96e0-0a8d81cdd004.xml"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_PSHED_PLUGIN_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: WHEA_PSHED_PLUGIN_CALLBACKS, *PWHEA_PSHED_PLUGIN_CALLBACKS
---

# _WHEA_PSHED_PLUGIN_CALLBACKS structure


## -description


The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in.


## -struct-fields




### -field GetAllErrorSources

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_all_error_sources">GetAllErrorSources</a> callback function. If a PSHED plug-in does not participate in error source discovery, this member should be set to <b>NULL</b>.


### -field Reserved

Reserved for system use. This member should be set to <b>NULL</b>.


### -field GetErrorSourceInfo

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_error_source_info">GetErrorSourceInfo</a> callback function. If a PSHED plug-in does not participate in error source discovery, this member should be set to <b>NULL</b>.


### -field SetErrorSourceInfo

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_set_error_source_info">SetErrorSourceInfo</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.


### -field EnableErrorSource

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_enable_error_source">EnableErrorSource</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.


### -field DisableErrorSource

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_disable_error_source">DisableErrorSource</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.


### -field WriteErrorRecord

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_write_error_record">WriteErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.


### -field ReadErrorRecord

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_read_error_record">ReadErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.


### -field ClearErrorRecord

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_clear_error_record">ClearErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.


### -field RetrieveErrorInfo

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_retrieve_error_info">RetrieveErrorInfo</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.


### -field FinalizeErrorRecord

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_finalize_error_record">FinalizeErrorRecord</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.


### -field ClearErrorStatus

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_clear_error_status">ClearErrorStatus</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.


### -field AttemptRecovery

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_attempt_error_recovery">AttemptRecovery</a> callback function. If a PSHED plug-in does not participate in error recovery, this member should be set to <b>NULL</b>.


### -field GetInjectionCapabilities

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_injection_capabilities">GetInjectionCapabilities</a> callback function. If a PSHED plug-in does not participate in error injection, this member should be set to <b>NULL</b>.


### -field InjectError

A pointer to the PSHED plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_inject_error">InjectError</a> callback function. If a PSHED plug-in does not participate in error injection, this member should be set to <b>NULL</b>.


## -remarks



A WHEA_PSHED_PLUGIN_CALLBACKS structure is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_attempt_error_recovery">AttemptRecovery</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_clear_error_record">ClearErrorRecord</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_clear_error_status">ClearErrorStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_disable_error_source">DisableErrorSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_enable_error_source">EnableErrorSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_finalize_error_record">FinalizeErrorRecord</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_all_error_sources">GetAllErrorSources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_error_source_info">GetErrorSourceInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_injection_capabilities">GetInjectionCapabilities</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_inject_error">InjectError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_read_error_record">ReadErrorRecord</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_retrieve_error_info">RetrieveErrorInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_set_error_source_info">SetErrorSourceInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_write_error_record">WriteErrorRecord</a>
 

 

