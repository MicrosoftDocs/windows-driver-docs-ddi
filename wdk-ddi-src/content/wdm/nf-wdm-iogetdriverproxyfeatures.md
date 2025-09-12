---
UID: NF:wdm.IoGetDriverProxyFeatures
tech.root: kernel
title: IoGetDriverProxyFeatures
ms.date: 09/05/2025
targetos: Windows
description: Gets the DriverProxy feature flags for the current system and the specified driver.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetDriverProxyFeatures
f1_keywords:
 - IoGetDriverProxyFeatures
 - wdm/IoGetDriverProxyFeatures
dev_langs:
 - c++
helpviewer_keywords:
 - IoGetDriverProxyFeatures
ai-usage: ai-assisted
---

## -description

The **IoGetDriverProxyFeatures** function gets the DriverProxy feature flags for the current system and the specified driver.

This function allows drivers to determine whether DriverProxy functionality is available and enabled for their specific driver instance. DriverProxy enables hot-swappable driver functionality by allowing drivers to register endpoint functions that can be replaced at runtime without unloading the driver.

## -parameters

### -param DriverObject

[in, optional] An optional pointer to the [**DRIVER_OBJECT**](ns-wdm-_driver_object.md) to check for DriverProxy support. If this parameter is NULL, the function checks whether DriverProxy is enabled for all drivers on the system.

### -param Flags

[out] A pointer to a [**DRIVER_PROXY_FEATURE_FLAGS**](ns-wdm-driver_proxy_feature_flags.md) structure that receives the DriverProxy feature flags. The structure indicates whether DriverProxy functionality is available and enabled.

## -returns

This function does not return a value.

## -remarks

The **IoGetDriverProxyFeatures** function determines DriverProxy availability based on several factors:

- Whether the system supports DriverProxy functionality
- Whether the Secure Kernel is running (required for DriverProxy)
- Whether the specific driver is excluded from DriverProxy operations via registry settings
- Whether DriverProxy has been globally disabled

Drivers should call this function before attempting to use other DriverProxy APIs such as [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md) or [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md).

The function can be called at any IRQL level and is safe to use during driver initialization.

## -see-also

[**DRIVER_PROXY_FEATURE_FLAGS**](ns-wdm-driver_proxy_feature_flags.md)

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)

[**DRIVER_OBJECT**](ns-wdm-_driver_object.md)
