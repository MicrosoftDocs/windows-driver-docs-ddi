---
UID: NF:wdm.PS_AVAILABLE_CPUS_CHANGE_CALLBACK
tech.root: kernel
title: PS_AVAILABLE_CPUS_CHANGE_CALLBACK
ms.date: 08/05/2025
targetos: Windows
description: The PS_AVAILABLE_CPUS_CHANGE_CALLBACK function is a callback routine that is called when the set of available CPUs changes.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL to DISPATCH_LEVEL
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
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PS_AVAILABLE_CPUS_CHANGE_CALLBACK
f1_keywords:
 - PS_AVAILABLE_CPUS_CHANGE_CALLBACK
 - wdm/PS_AVAILABLE_CPUS_CHANGE_CALLBACK
dev_langs:
 - c++
helpviewer_keywords:
 - PS_AVAILABLE_CPUS_CHANGE_CALLBACK
---

## -description

The **PS_AVAILABLE_CPUS_CHANGE_CALLBACK** function is a callback routine that is called when the set of available CPUs changes for a process or the system.

## -parameters

### -param Context [in, optional]

A pointer to driver-defined context information that was specified when the callback was registered with [**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md) or [**PsRegisterSystemAvailableCpusChangeNotification**](nf-wdm-psregistersystemavailablecpuschangenotification.md).

### -param SequenceNumber [in]

The current sequence number for the available CPUs. This value increments whenever the set of available CPUs changes.

## -remarks

This callback function is implemented by the driver and is called by the system when CPU availability changes.

The callback can be invoked at IRQL from PASSIVE_LEVEL to DISPATCH_LEVEL, so the implementation must be able to run at DISPATCH_LEVEL.

### When the Callback is Invoked

The callback is invoked when:

- CPUs are added or removed from the system (hotplug scenarios)
- Process affinity is modified (for process-specific registrations)
- System-wide CPU availability changes (for system registrations)
- CPU cores go online or offline
- Processor groups are modified

### Implementation Guidelines

- The callback should complete quickly since it may be called at DISPATCH_LEVEL
- Avoid blocking operations or lengthy processing
- Use the **SequenceNumber** parameter to detect and handle changes efficiently
- Query the current CPU availability using [**PsQueryProcessAvailableCpus**](nf-wdm-psqueryprocessavailablecpus.md) or [**PsQuerySystemAvailableCpus**](nf-wdm-psquerysystemavailablecpus.md) if needed

## -see-also

[**PsRegisterProcessAvailableCpusChangeNotification**](nf-wdm-psregisterprocessavailablecpuschangenotification.md)

[**PsRegisterSystemAvailableCpusChangeNotification**](nf-wdm-psregistersystemavailablecpuschangenotification.md)

[**PsUnregisterAvailableCpusChangeNotification**](nf-wdm-psunregisteravailablecpuschangenotification.md)

[**PsQueryProcessAvailableCpus**](nf-wdm-psqueryprocessavailablecpus.md)

[**PsQuerySystemAvailableCpus**](nf-wdm-psquerysystemavailablecpus.md)
