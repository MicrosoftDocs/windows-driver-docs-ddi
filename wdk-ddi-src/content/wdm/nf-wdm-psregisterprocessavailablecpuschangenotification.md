---
UID: NF:wdm.PsRegisterProcessAvailableCpusChangeNotification
tech.root: kernel
title: PsRegisterProcessAvailableCpusChangeNotification
ms.date: 08/05/2025
targetos: Windows
description: The PsRegisterProcessAvailableCpusChangeNotification function registers a callback to be called when the CPUs that are available to a process undergo a change.
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
 - PsRegisterProcessAvailableCpusChangeNotification
f1_keywords:
 - PsRegisterProcessAvailableCpusChangeNotification
 - wdm/PsRegisterProcessAvailableCpusChangeNotification
dev_langs:
 - c++
helpviewer_keywords:
 - PsRegisterProcessAvailableCpusChangeNotification
---

## -description

The **PsRegisterProcessAvailableCpusChangeNotification** function registers a callback to be called when the CPUs that are available to a process undergo a change.

## -parameters

### -param Process [in]

Pointer to a process (PEPROCESS).

### -param Callback [in]

The callback function to be called. This parameter is of type [**PS_AVAILABLE_CPUS_CHANGE_CALLBACK**](nf-wdm-ps_available_cpus_change_callback.md).

### -param Context [in, optional]

Pointer to a context parameter that will be passed to the callback function.

### -param ObservedSequenceNumber [in, optional]

Optionally supplies a pointer to the most recent available CPUs sequence number observed by the caller. If the sequence number has advanced since that observation, a callback will be made immediately.

### -param RegistrationHandle [out]

Supplies a pointer to a buffer that upon success receives a handle to the callback registration (PS_AVAILABLE_CPUS_CHANGE_REGISTRATION).

## -returns

**PsRegisterProcessAvailableCpusChangeNotification** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The callback was registered successfully. |
| **STATUS_INSUFFICIENT_RESOURCES** | The callback could not be registered due to insufficient system resources. |

## -remarks

This routine must be called at PASSIVE_LEVEL.

The callback will be invoked whenever the set of available CPUs for the specified process changes. This can occur due to CPU hotplug operations, process affinity changes, or other system events.

To unregister the callback, call [**PsUnregisterAvailableCpusChangeNotification**](nf-wdm-psunregisteravailablecpuschangenotification.md) with the registration handle returned by this function.

If an **ObservedSequenceNumber** is provided and the current sequence number has advanced beyond it, the callback will be invoked immediately upon registration.

## -see-also

[**PsUnregisterAvailableCpusChangeNotification**](nf-wdm-psunregisteravailablecpuschangenotification.md)

[**PsRegisterSystemAvailableCpusChangeNotification**](nf-wdm-psregistersystemavailablecpuschangenotification.md)

[**PS_AVAILABLE_CPUS_CHANGE_CALLBACK**](nf-wdm-ps_available_cpus_change_callback.md)
