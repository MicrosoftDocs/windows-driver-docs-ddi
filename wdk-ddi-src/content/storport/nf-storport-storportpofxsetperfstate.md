---
UID: NF:storport.StorPortPoFxSetPerfState
tech.root: storage
title: StorPortPoFxSetPerfState
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: StorPortPoFxSetPerfState sets a component's P-state.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - storport.h
api_name:
 - StorPortPoFxSetPerfState
f1_keywords:
 - StorPortPoFxSetPerfState
 - storport/StorPortPoFxSetPerfState
dev_langs:
 - c++
---

## -description

**StorPortPoFxSetPerfState** sets a component's P-state (performance or "perf" state).

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param Address

Address of the device being registered. Currently only adapters are supported, so **Address** must be NULL.

### -param Component

The index that identifies the component whose P-states will be managed. This parameter is an index into the **Components**array in the [**STOR_POFX_DEVICE**](ns-storport-_stor_pofx_device_v3.md) structure that the miniport used to register the device for Storport PoFx support. If the **Components** array contains N elements, component indexes range from 0 to N–1.

### -param Flags

Currently must be set to NULL.

### -param SetIndex

The index of a previously registered perf set.

### -param State

If the perf set contains discrete P-States, this should be an index value. If the perf set is a range, this should be a value within that range.

### -param Context

An arbitrary context that will be passed to the perf set change callback.

## -returns

**StorPortPoFxSetPerfState** returns STOR_STATUS_SUCCESS upon successful completion or if runtime power has been disabled, or an error code such as one of the following:

| Error code | Meaning |
| ---------- | ------- |
| STOR_STATUS_INVALID_PARAMETER | One of the parameters is invalid; for example, **Address** or **Flags** are not NULL. |
| STOR_STATUS_UNSUCCESSFUL | The adapter isn't registered for idle detection. |

## -remarks

## -see-also
