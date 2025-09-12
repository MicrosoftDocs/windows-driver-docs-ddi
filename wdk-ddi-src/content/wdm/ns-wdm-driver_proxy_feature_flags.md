---
UID: NS:wdm._DRIVER_PROXY_FEATURE_FLAGS
tech.root: kernel
title: DRIVER_PROXY_FEATURE_FLAGS
ms.date: 09/05/2025
targetos: Windows
description: Contains feature flags that indicate DriverProxy functionality availability and status.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.typenames: DRIVER_PROXY_FEATURE_FLAGS, *PDRIVER_PROXY_FEATURE_FLAGS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_PROXY_FEATURE_FLAGS
 - PDRIVER_PROXY_FEATURE_FLAGS
 - DRIVER_PROXY_FEATURE_FLAGS
f1_keywords:
 - _DRIVER_PROXY_FEATURE_FLAGS
 - wdm/_DRIVER_PROXY_FEATURE_FLAGS
 - PDRIVER_PROXY_FEATURE_FLAGS
 - wdm/PDRIVER_PROXY_FEATURE_FLAGS
 - DRIVER_PROXY_FEATURE_FLAGS
 - wdm/DRIVER_PROXY_FEATURE_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DRIVER_PROXY_FEATURE_FLAGS
ai-usage: ai-assisted
---

## -description

The **DRIVER_PROXY_FEATURE_FLAGS** structure contains feature flags that indicate the availability and status of DriverProxy functionality for the current system and driver.

## -struct-fields

### -field AsUlong

The complete set of feature flags as a single **ULONG** value. This provides access to all flags as a 32-bit integer for easy initialization, comparison, or storage.

### -field Enabled

A single-bit flag that indicates whether DriverProxy functionality is enabled and available. When this bit is set to **1**, DriverProxy APIs such as [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md) and [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md) can be used successfully. When this bit is **0**, DriverProxy functionality is not available.

### -field Reserved

Reserved bits for future use. These bits are currently unused and should be ignored by drivers. They are reserved for potential future expansion of DriverProxy feature flags.

## -remarks

This structure is used by [**IoGetDriverProxyFeatures**](nf-wdm-iogetdriverproxyfeatures.md) to return information about whether DriverProxy hot-swappable functionality is supported and enabled. Drivers should call this function to retrieve the structure and check the **Enabled** flag before attempting to use DriverProxy APIs.

The **Enabled** flag is set based on several system conditions, including:

- The Secure Kernel must be running
- The system must be configured for DriverProxy operations
- The driver must not be excluded from DriverProxy functionality via registry settings
- DriverProxy must not be globally disabled

Drivers should initialize this structure to zero before passing it to [**IoGetDriverProxyFeatures**](nf-wdm-iogetdriverproxyfeatures.md) to ensure that any uninitialized bits do not contain random values.

## -see-also

[**IoGetDriverProxyFeatures**](nf-wdm-iogetdriverproxyfeatures.md)

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)
