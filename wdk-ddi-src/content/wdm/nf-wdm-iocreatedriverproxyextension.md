---
UID: NF:wdm.IoCreateDriverProxyExtension
tech.root: kernel
title: IoCreateDriverProxyExtension
ms.date: 09/05/2025
targetos: Windows
description: Allocates and initializes a DriverProxy extension.
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
 - IoCreateDriverProxyExtension
f1_keywords:
 - IoCreateDriverProxyExtension
 - wdm/IoCreateDriverProxyExtension
dev_langs:
 - c++
helpviewer_keywords:
 - IoCreateDriverProxyExtension
ai-usage: ai-assisted
---

## -description

The **IoCreateDriverProxyExtension** function allocates and initializes a DriverProxy extension that enables hot-swappable driver functionality.

## -parameters

### -param OwningDriverObject

[in, optional] An optional pointer to the [**DRIVER_OBJECT**](ns-wdm-driver_object.md) that will own the DriverProxy extension. If provided, the extension will be associated with this driver object. If NULL, the extension is created without an owning driver.

### -param Flags

[in] A [**DRIVER_PROXY_EXTENSION_CREATION_FLAGS**](ns-wdm-driver_proxy_extension_creation_flags.md) value that provides additional configuration options for extension creation. Currently, no flags are defined, so this parameter should be set to 0.

### -param DriverProxyExtension

[out] A pointer to a variable that receives a pointer to the newly created DriverProxy extension. This extension can be used with other DriverProxy APIs.

## -returns

**IoCreateDriverProxyExtension** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The extension was successfully allocated and initialized. |
| **STATUS_NOT_SUPPORTED** | The current system does not support DriverProxy extensions. |
| **STATUS_DRIVER_BLOCKED** | The specified driver is excluded from DriverProxy operations via registry settings. |
| **STATUS_INSUFFICIENT_RESOURCES** | Insufficient memory was available to allocate the extension. |
| **STATUS_RESOURCE_IN_USE** | The specified driver object already owns a DriverProxy extension. |

## -remarks

A DriverProxy extension is required for any driver that wants to use Driver Hot-Swap functionality. The extension serves as an opaque token that holds all relevant DriverProxy information and enables hot-swappable operations.

Drivers using Driver Hot-Swap should create a DriverProxy extension during [**DriverEntry**](/windows-hardware/drivers/kernel/writing-a-driverentry-routine), preferably early in the function. It is recommended to store the result in a global variable for easy access throughout the driver's lifetime.

Before calling **IoCreateDriverProxyExtension**, drivers should call [**IoGetDriverProxyFeatures**](nf-wdm-iogetdriverproxyfeatures.md) to verify that DriverProxy functionality is available and enabled.

Each driver object can own at most one DriverProxy extension. If a driver object already has an associated extension, the function returns **STATUS_RESOURCE_IN_USE**.

In Driver Hot-Swap V2, once the extension is successfully created, endpoint wrappers are automatically available without requiring explicit registration calls. The compiler and linker automatically generate the endpoint information during the build process.

The system automatically manages the lifecycle of the DriverProxy extension. When the owning driver object is unloaded, the extension is automatically cleaned up.

## -see-also

- [**IoGetDriverProxyFeatures**](nf-wdm-iogetdriverproxyfeatures.md)
- [**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md)
- [**IoGetDriverProxyExtensionFromDriverObject**](nf-wdm-iogetdriverproxyextensionfromdriverobject.md)
- [**DRIVER_PROXY_EXTENSION_CREATION_FLAGS**](ns-wdm-driver_proxy_extension_creation_flags.md)
- [**DRIVER_OBJECT**](ns-wdm-driver_object.md)
