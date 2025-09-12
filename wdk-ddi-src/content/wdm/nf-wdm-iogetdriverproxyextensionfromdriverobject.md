---
UID: NF:wdm.IoGetDriverProxyExtensionFromDriverObject
tech.root: kernel
title: IoGetDriverProxyExtensionFromDriverObject
ms.date: 09/05/2025
targetos: Windows
description: Gets the DriverProxy extension owned by a driver object.
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
 - IoGetDriverProxyExtensionFromDriverObject
f1_keywords:
 - IoGetDriverProxyExtensionFromDriverObject
 - wdm/IoGetDriverProxyExtensionFromDriverObject
dev_langs:
 - c++
helpviewer_keywords:
 - IoGetDriverProxyExtensionFromDriverObject
ai-usage: ai-assisted
---

## -description

The **IoGetDriverProxyExtensionFromDriverObject** function retrieves the DriverProxy extension that is owned by the specified driver object.

## -parameters

### -param DriverObject

[in] A pointer to the [**DRIVER_OBJECT**](ns-wdm-driver_object.md) that owns the DriverProxy extension to retrieve.

## -returns

**IoGetDriverProxyExtensionFromDriverObject** returns a pointer to the DriverProxy extension owned by the specified driver object, or NULL if the driver object does not have an associated DriverProxy extension.

## -remarks

This function provides a simple way to retrieve an existing DriverProxy extension that was previously created with [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md) and associated with a driver object, without needing to store the extension pointer separately. The function is commonly used when a driver needs to access its DriverProxy extension from different parts of its code.

The function can be called at any IRQL level and does not perform any memory allocation or complex operations.

If the driver object's **DriverExtension** field is NULL, the function will return NULL and may trigger an assertion in debug builds.

## -see-also

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)

[**DRIVER_OBJECT**](ns-wdm-driver_object.md)
