---
UID: NC:ntddk.PSHED_PI_CLEAR_ERROR_RECORD
title: PSHED_PI_CLEAR_ERROR_RECORD (ntddk.h)
description: A PSHED plug-in's ClearErrorRecord callback function clears the specified error record from the system's persistent data storage.
old-location: whea\clearerrorrecord.htm
tech.root: whea
ms.assetid: e9893f9c-7fbd-4a02-8c2d-d7c480ed5198
ms.date: 02/20/2018
ms.keywords: ClearErrorRecord, ClearErrorRecord callback function [WHEA Drivers and Applications], PSHED_PI_CLEAR_ERROR_RECORD, PSHED_PI_CLEAR_ERROR_RECORD callback, ntddk/ClearErrorRecord, whea.clearerrorrecord, whearef_1644b60c-c232-4cca-805b-d6a061425f61.xml
f1_keywords:
 - "ntddk/ClearErrorRecord"
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
- ClearErrorRecord
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_CLEAR_ERROR_RECORD callback function


## -description


A PSHED plug-in's <i>ClearErrorRecord </i>callback function clears the specified error record from the system's persistent data storage.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the clear operation. No flags are currently defined.


### -param ErrorRecordId [in]

The identifier of the error record that is being cleared from the system's persistent data storage. This identifier should be compared to the <b>Header.RecordId</b> member of each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure that has been written to the system's persistent data storage to identify the error record to be cleared.


## -returns



A PSHED plug-in's <i>ClearErrorRecord</i> callback function returns one of the following NTSTATUS codes:

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
The error record was successfully cleared from the system's persistent data storage.

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



A PSHED plug-in that participates in error record persistence sets the <b>Callbacks.WriteErrorRecord</b>, <b>Callbacks.ReadErrorRecord </b>and <b>Callbacks.ClearErrorRecord </b>members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_write_error_record">WriteErrorRecord</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_read_error_record">ReadErrorRecord</a>, and <i>ClearErrorRecord</i> callback functions when the plug-in calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorRecordPersistence</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to clear an error record from the system's persistent data storage. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's <i>ClearErrorRecord</i> callback function to perform the clear operation. The mechanism that is used to clear the error record from the system's persistent data storage is platform-specific.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_read_error_record">ReadErrorRecord</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_write_error_record">WriteErrorRecord</a>
 

 

