---
UID: NC:ntddk.PSHED_PI_ATTEMPT_ERROR_RECOVERY
title: PSHED_PI_ATTEMPT_ERROR_RECOVERY (ntddk.h)
description: A PSHED plug-in's AttemptRecovery callback function attempts to recover from a recoverable hardware error.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_ATTEMPT_ERROR_RECOVERY callback function"]
ms.keywords: AttemptRecovery, AttemptRecovery callback function [WHEA Drivers and Applications], PSHED_PI_ATTEMPT_ERROR_RECOVERY, PSHED_PI_ATTEMPT_ERROR_RECOVERY callback, ntddk/AttemptRecovery, whea.attemptrecovery, whearef_e6307253-0f45-4613-b384-ad737da27031.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt:
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
req.irql: IRQL >= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PSHED_PI_ATTEMPT_ERROR_RECOVERY
 - ntddk/PSHED_PI_ATTEMPT_ERROR_RECOVERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_ATTEMPT_ERROR_RECOVERY
---

## -description

A PSHED plug-in's *AttemptRecovery* callback function attempts to recover from a recoverable hardware error.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param BufferLength [in]

The size, in bytes, of the error record that is pointed to by the *ErrorRecord* parameter.

### -param ErrorRecord [in]

A pointer to a [**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record) structure that describes an error record for a recoverable hardware error.

## -returns

A PSHED plug-in's *AttemptRecovery* callback function returns one of the following NTSTATUS codes.

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The attempt to recover from the hardware error was successful. |
| **STATUS_UNSUCCESSFUL** | The attempt to recover from the hardware error was unsuccessful. |

## -remarks

A PSHED plug-in that participates in error recovery sets the **Callbacks.AttemptRecovery** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its *AttemptRecovery* callback function when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorRecovery** flag in the **FunctionalAreaMask** member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel attempts to recover from a recoverable hardware error while it processes the error after all of the hardware error data has been put into the error record. The Windows kernel then calls into the PSHED to give it an opportunity to perform any required recovery operations. If a PSHED plug-in is registered to participate in error recovery, the PSHED calls the PSHED plug-in's *AttemptRecovery* callback function so that it can attempt to correct the error and/or perform any additional operations that are required to fully recover from the error condition.

If the Windows kernel or the PSHED successfully recovers from the hardware error, it updates the [**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record) structure that describes the error before it calls the PSHED plug-in's *AttemptRecovery* callback function as follows:

- The **Header.Severity** member is changed from **WheaErrSevRecoverable** to **WheaErrSevCorrected**.

- The **Header.Flags.Recovered** bit is set.

If the PSHED plug-in successfully recovers from the hardware error, the PSHED will update the WHEA_ERROR_RECORD structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's *AttemptRecovery* callback function returns. A PSHED plug-in's *AttemptRecovery* callback function should not modify the error record.

The PSHED calls a PSHED plug-in's *AttemptRecovery* callback function at IRQL <= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.

## -see-also

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
