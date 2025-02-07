---
UID: NE:d3dukmdt._D3DDDI_QUERYREGISTRY_TYPE
title: D3DDDI_QUERYREGISTRY_TYPE (d3dukmdt.h)
description: Used to query the registry type.
ms.date: 02/06/2025
req.header: d3dukmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DDDI_QUERYREGISTRY_TYPE
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDI_QUERYREGISTRY_TYPE
 - d3dukmdt/_D3DDDI_QUERYREGISTRY_TYPE
 - D3DDDI_QUERYREGISTRY_TYPE
 - d3dukmdt/D3DDDI_QUERYREGISTRY_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_QUERYREGISTRY_TYPE
 - D3DDDI_QUERYREGISTRY_TYPE
---

# D3DDDI_QUERYREGISTRY_TYPE enumeration

## -description

**D3DDDI_QUERYREGISTRY_TYPE** enumeration values indicate which data to retrieve through [**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md) for [**D3DDDI_QUERYADAPTERTYPE_QUERYREGISTRY**](../d3dumddi/ne-d3dumddi-_d3dddi_queryadaptertype.md).

## -enum-fields

### -field D3DDDI_QUERYREGISTRY_SERVICEKEY

Indicates to retrieve registry data from the service hive. The registry path is `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services\<ServiceName>`.

See [Introduction to Registry Keys for Drivers](/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers) for more details, where it is referred to as the driver's Parameters key.

### -field D3DDDI_QUERYREGISTRY_ADAPTERKEY

Indicates to retrieve registry data from the adapter hive. The registry path is `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4d36e968-e325-11ce-bfc1-08002be10318}\<Number>`.

See [Introduction to Registry Keys for Drivers](/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers) for more details, where it is referred to as the driver's Software key.

### -field D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH

Indicates to retrieve the driver store path for the adapter. The full driver store path is returned in [**D3DDDI_QUERYREGISTRY_INFO::OutputString**](ns-d3dukmdt-_d3dddi_queryregistry_info.md). The path is returned in the form of `<SystemDrive>:\system32\DriverStore\FileRepository\<DriverString>`.

### -field D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH

Indicates to retrieve the driver image path, which includes the driver name associated with [**DriverEntry**](/windows-hardware/drivers/display/driverentry-of-display-miniport-driver).

### -field D3DDDI_QUERYREGISTRY_MAX

Max value for this enum; don't use.

## -see-also

[**D3DDDI_QUERYADAPTERTYPE**](../d3dumddi/ne-d3dumddi-_d3dddi_queryadaptertype.md)

[**D3DDDI_QUERYREGISTRY_INFO**](ns-d3dukmdt-_d3dddi_queryregistry_info.md)

[**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md)
