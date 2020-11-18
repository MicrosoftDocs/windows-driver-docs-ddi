---
UID: NF:wdfdriver.WdfDriverOpenPersistentStateRegistryKey
title: WdfDriverOpenPersistentStateRegistryKey
tech.root: wdf
ms.date: 
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdfdriver.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 2.25
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1909
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 1.25
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdfdriver.h
api_name:
 - WdfDriverOpenPersistentStateRegistryKey
f1_keywords:
 - WdfDriverOpenPersistentStateRegistryKey
 - wdfdriver/WdfDriverOpenPersistentStateRegistryKey
dev_langs:
 - c++
---

## -description

Drivers should use **WdfDriverOpenPersistentStateRegistryKey** to write driver wide persistent information to the registry. 

## -parameters

### -param Driver

[in]
A handle to the driver's framework driver object that the driver obtained from a previous call to [**WdfDriverCreate**](./nf-wdfdriver-wdfdrivercreate.md) or [**WdfGetDriver**](./nf-wdfdriver-wdfgetdriver.md).

### -param DesiredAccess

[in]
An [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) typed value that specifies an access mask for the registry key.
A KMDF driver typically requests **KEY_READ**, **KEY_WRITE**, or **KEY_READ** | **KEY_WRITE**.
If you are writing a UMDF driver, use **KEY_READ** or **KEY_READ** | **KEY_SET_VALUE**.
As a best practice, ask for only the types of access that your driver needs.

### -param KeyAttributes

[in, optional]
A pointer to a caller-allocated [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that specifies object attributes for the framework registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.
 
### -param Key

[out]
A pointer to a location that receives a handle to a framework registry-key object.

## -returns

Refer to [**WdfDriverOpenParametersRegistryKey**](./nf-wdfdriver-wdfdriveropenparametersregistrykey.md).

## -remarks

The `Parameters` key is for *immutable* settings provided in the INF file.  To access those settings, use [**WdfDriverOpenParametersRegistryKey**](./nf-wdfdriver-wdfdriveropenparametersregistrykey.md).  The key returned from this API is for settings written at runtime.

## -see-also

[**WdfDriverOpenParametersRegistryKey**](./nf-wdfdriver-wdfdriveropenparametersregistrykey.md)

[**IoOpenDriverRegistryKey**](../wdm/nf-wdm-ioopendriverregistrykey.md)

[**DRIVER_REGKEY_TYPE**](../wdm/ne-wdm-driver_regkey_type.md)