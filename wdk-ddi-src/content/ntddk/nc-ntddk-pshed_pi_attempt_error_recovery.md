---
UID: NC:ntddk.PSHED_PI_ATTEMPT_ERROR_RECOVERY
title: PSHED_PI_ATTEMPT_ERROR_RECOVERY
author: windows-driver-content
description: A PSHED plug-in's AttemptRecovery callback function attempts to recover from a recoverable hardware error.
old-location: whea\attemptrecovery.htm
old-project: whea
ms.assetid: e7186c16-f093-4a64-aa25-03e9ce0f967e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
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
req.alt-api: AttemptRecovery
req.alt-loc: Ntddk.h
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
req.typenames: *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
---

# PSHED_PI_ATTEMPT_ERROR_RECOVERY callback



## -description
A PSHED plug-in's <i>AttemptRecovery</i> callback function attempts to recover from a recoverable hardware error.



## -prototype

````
PSHED_PI_ATTEMPT_ERROR_RECOVERY AttemptRecovery;

NTSTATUS AttemptRecovery(
  _Inout_opt_ PVOID              PluginContext,
  _In_        ULONG              BufferLength,
  _In_        PWHEA_ERROR_RECORD ErrorRecord
)
{ ... }
````


## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param BufferLength [in]

The size, in bytes, of the error record that is pointed to by the <i>ErrorRecord</i> parameter.


### -param ErrorRecord [in]

A pointer to a <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure that describes an error record for a recoverable hardware error.


## -returns
A PSHED plug-in's <i>AttemptRecovery</i> callback function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The attempt to recover from the hardware error was successful.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The attempt to recover from the hardware error was unsuccessful.

 


## -remarks
A PSHED plug-in that participates in error recovery sets the <b>Callbacks.AttemptRecovery</b> member of the <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <i>AttemptRecovery</i> callback function when the plug-in calls the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorRecovery</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel attempts to recover from a recoverable hardware error while it processes the error after all of the hardware error data has been put into the error record. The Windows kernel then calls into the PSHED to give it an opportunity to perform any required recovery operations. If a PSHED plug-in is registered to participate in error recovery, the PSHED calls the PSHED plug-in's <i>AttemptRecovery</i> callback function so that it can attempt to correct the error and/or perform any additional operations that are required to fully recover from the error condition.

If the Windows kernel or the PSHED successfully recovers from the hardware error, it updates the <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure that describes the error before it calls the PSHED plug-in's <i>AttemptRecovery</i> callback function as follows: 

The <b>Header.Severity</b> member is changed from <b>WheaErrSevRecoverable</b> to <b>WheaErrSevCorrected</b>.

The <b>Header.Flags.Recovered</b> bit is set.

If the PSHED plug-in successfully recovers from the hardware error, the PSHED will update the WHEA_ERROR_RECORD structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's <i>AttemptRecovery</i> callback function returns. A PSHED plug-in's <i>AttemptRecovery</i> callback function should not modify the error record.

The PSHED calls a PSHED plug-in's <i>AttemptRecovery</i> callback function at IRQL &lt;= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_ATTEMPT_ERROR_RECOVERY callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

