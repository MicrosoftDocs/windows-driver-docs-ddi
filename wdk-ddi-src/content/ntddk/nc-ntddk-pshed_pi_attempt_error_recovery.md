---
UID: NC:ntddk.PSHED_PI_ATTEMPT_ERROR_RECOVERY
title: PSHED_PI_ATTEMPT_ERROR_RECOVERY (ntddk.h)
description: A PSHED plug-in's AttemptRecovery callback function attempts to recover from a recoverable hardware error.
old-location: whea\attemptrecovery.htm
tech.root: whea
ms.assetid: e7186c16-f093-4a64-aa25-03e9ce0f967e
ms.date: 02/20/2018
ms.keywords: AttemptRecovery, AttemptRecovery callback function [WHEA Drivers and Applications], PSHED_PI_ATTEMPT_ERROR_RECOVERY, PSHED_PI_ATTEMPT_ERROR_RECOVERY callback, ntddk/AttemptRecovery, whea.attemptrecovery, whearef_e6307253-0f45-4613-b384-ad737da27031.xml
f1_keywords:
 - "ntddk/AttemptRecovery"
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
req.irql: <= HIGH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- AttemptRecovery
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSHED_PI_ATTEMPT_ERROR_RECOVERY callback function


## -description


A PSHED plug-in's <i>AttemptRecovery</i> callback function attempts to recover from a recoverable hardware error.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param BufferLength [in]

The size, in bytes, of the error record that is pointed to by the <i>ErrorRecord</i> parameter.


### -param ErrorRecord [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure that describes an error record for a recoverable hardware error.


## -returns



A PSHED plug-in's <i>AttemptRecovery</i> callback function returns one of the following NTSTATUS codes.

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
The attempt to recover from the hardware error was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The attempt to recover from the hardware error was unsuccessful.

</td>
</tr>
</table>
 




## -remarks



A PSHED plug-in that participates in error recovery sets the <b>Callbacks.AttemptRecovery</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>AttemptRecovery</i> callback function when the plug-in calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorRecovery</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel attempts to recover from a recoverable hardware error while it processes the error after all of the hardware error data has been put into the error record. The Windows kernel then calls into the PSHED to give it an opportunity to perform any required recovery operations. If a PSHED plug-in is registered to participate in error recovery, the PSHED calls the PSHED plug-in's <i>AttemptRecovery</i> callback function so that it can attempt to correct the error and/or perform any additional operations that are required to fully recover from the error condition.

If the Windows kernel or the PSHED successfully recovers from the hardware error, it updates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure that describes the error before it calls the PSHED plug-in's <i>AttemptRecovery</i> callback function as follows: 

<ul>
<li>
The <b>Header.Severity</b> member is changed from <b>WheaErrSevRecoverable</b> to <b>WheaErrSevCorrected</b>.

</li>
<li>
The <b>Header.Flags.Recovered</b> bit is set.

</li>
</ul>
If the PSHED plug-in successfully recovers from the hardware error, the PSHED will update the WHEA_ERROR_RECORD structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's <i>AttemptRecovery</i> callback function returns. A PSHED plug-in's <i>AttemptRecovery</i> callback function should not modify the error record.

The PSHED calls a PSHED plug-in's <i>AttemptRecovery</i> callback function at IRQL <= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
 

 

