---
UID: NS:wdm._DRIVER_PROXY_EXTENSION_CREATION_FLAGS
tech.root: kernel
title: DRIVER_PROXY_EXTENSION_CREATION_FLAGS
ms.date: 09/11/2025
targetos: Windows
description: Contains flags for configuring DriverProxy extension creation.
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
req.typenames: DRIVER_PROXY_EXTENSION_CREATION_FLAGS, *PDRIVER_PROXY_EXTENSION_CREATION_FLAGS
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
 - _DRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - PDRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - DRIVER_PROXY_EXTENSION_CREATION_FLAGS
f1_keywords:
 - _DRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - wdm/_DRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - PDRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - wdm/PDRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - DRIVER_PROXY_EXTENSION_CREATION_FLAGS
 - wdm/DRIVER_PROXY_EXTENSION_CREATION_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DRIVER_PROXY_EXTENSION_CREATION_FLAGS
ai-usage: ai-assisted
---

## -description

The **DRIVER_PROXY_EXTENSION_CREATION_FLAGS** structure contains configuration flags for DriverProxy extension creation.

## -struct-fields

### -field AsUlong

The complete set of creation flags as a single **ULONG** value. This provides access to all flags as a 32-bit integer for easy initialization, comparison, or storage. Currently, this value should always be 0.

### -field ReservedZero

A 32-bit field that is reserved and must be set to zero. This field is reserved for potential future expansion of DriverProxy extension creation options.

## -remarks

The **DRIVER_PROXY_EXTENSION_CREATION_FLAGS** structure is designed as a union that allows access to the creation flags either as individual bit fields or as a complete **ULONG** value.

Currently, no configuration flags are defined for DriverProxy extension creation. Drivers should initialize this structure to zero before passing it to [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md).

## -see-also

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)
