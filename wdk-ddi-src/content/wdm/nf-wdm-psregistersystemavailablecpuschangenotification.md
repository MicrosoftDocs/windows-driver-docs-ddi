---
UID: NF:wdm.PsRegisterSystemAvailableCpusChangeNotification
tech.root: kernel
title: PsRegisterSystemAvailableCpusChangeNotification
ms.date: 08/05/2025
targetos: Windows
description: The PsRegisterSystemAvailableCpusChangeNotification function registers a callback to be called when the CPUs that are available to the system process undergo a change.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PsRegisterSystemAvailableCpusChangeNotification
f1_keywords:
 - PsRegisterSystemAvailableCpusChangeNotification
 - wdm/PsRegisterSystemAvailableCpusChangeNotification
dev_langs:
 - c++
helpviewer_keywords:
 - PsRegisterSystemAvailableCpusChangeNotification
---

## -description

The **PsRegisterSystemAvailableCpusChangeNotification** function registers a callback to be called when the CPUs that are available to the system process undergo a change.

## -parameters

### -param Callback [in]

Pointer to the callback function to be called. This parameter is of type [**PS_AVAILABLE_CPUS_CHANGE_CALLBACK**](nf-wdm-ps_available_cpus_change_callback.md).

### -param Context [in, optional]

Supplies a context parameter that will be passed to the callback function.

### -param ObservedSequenceNumber [in, optional]

Optional pointer to the most recent available CPUs sequence number observed by the caller. If the sequence number has advanced since that observation, a callback will be made immediately.

### -param RegistrationHandle [out]

Pointer to a buffer that upon success receives a handle to the callback registration (PS_AVAILABLE_CPUS_CHANGE_REGISTRATION).

## -returns

**PsRegisterSystemAvailableCpusChangeNotification** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The callback was registered successfully. |
| **STATUS_INSUFFICIENT_RESOURCES** | The callback could not be registered due to insufficient system resources. |

## -remarks

This routine must be called at PASSIVE_LEVEL.

The callback will be invoked whenever the set of available CPUs for the system process changes. This can occur due to CPU hotplug operations or other system events that affect overall CPU availability.

To unregister the callback, call [**PsUnregisterAvailableCpusChangeNotification**](nf-wdm-psunregisteravailablecpuschangenotification.md) with the registration handle returned by this function.

If an **ObservedSequenceNumber** is provided and the current sequence number has advanced beyond it, the callback will be invoked immediately upon registration.

This function monitors system-wide CPU availability changes, as opposed to process-specific changes monitored by [**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md).

## -see-also

[**PsUnregisterAvailableCpusChangeNotification**](nf-wdm-psunregisteravailablecpuschangenotification.md)

[**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md)

[**PS_AVAILABLE_CPUS_CHANGE_CALLBACK**](nf-wdm-ps_available_cpus_change_callback.md)
