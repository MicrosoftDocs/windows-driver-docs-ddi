---
UID: NF:storport.StorPortPoFxSetIdleTimeout
tech.root: storage
title: StorPortPoFxSetIdleTimeout
ms.date: 06/21/2022
targetos: Windows
description: Learn more about the StorPortPoFxSetIdleTimeout function.
prerelease: false
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
 - StorPortPoFxSetIdleTimeout
f1_keywords:
 - StorPortPoFxSetIdleTimeout
 - storport/StorPortPoFxSetIdleTimeout
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortPoFxSetIdleTimeout
---

## -description

A miniport can call **StorPortPoFxSetIdleTimeout** to set the idle timeout value for an adapter, which is the amount of time that an adapter can be idle before it gets the Device Power Not Required notification.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's device extension.

### -param Address

[in] Must be set to NULL because this function is only supported for adapters. Do not pass in the address of a unit.

### -param IdleTimeoutInMS

The idle timeout interval to use, in milliseconds.

## -returns

**StorPortPoFxSetIdleTimeout** returns STOR_STATUS_SUCCESS if runtime power has been disabled or if the idle timeout value was set successfully. Otherwise, it returns an error code such as one of the following.

| Error code | Meaning |
| ---------- | ------- |
| STOR_STATUS_INVALID_PARAMETER | A unit address was passed in. |
| STOR_STATUS_UNSUCCESSFUL | The [**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md) function was not previously successfully called for the adapter, or an idle timeout value was not set. |

## -remarks

If the STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT flag was specified and the **AdapterIdleTimeoutInMS** set when the adapter was registered for runtime power management, that value will be overridden by **IdleTimeoutInMS** value passed to this function. See [**STOR_POFX_DEVICE_V3**](ns-storport-_stor_pofx_device_v3.md) for information on how to register for runtime power management.

A miniport can only call this function if it previously called [**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md) for the adapter.

## -see-also

[**STOR_POFX_DEVICE_V3**](ns-storport-_stor_pofx_device_v3.md)

[**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md)
