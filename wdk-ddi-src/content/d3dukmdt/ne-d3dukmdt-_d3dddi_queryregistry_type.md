---
UID: NE:d3dukmdt._D3DDDI_QUERYREGISTRY_TYPE
title: _D3DDDI_QUERYREGISTRY_TYPE (d3dukmdt.h)
description: Used to query the registry type.
ms.assetid: c01641d0-ff58-4e3a-9f2e-e8918c84b4b5
ms.date: 11/21/2018
ms.topic: enum
f1_keywords:
 - "d3dukmdt/_D3DDDI_QUERYREGISTRY_TYPE"
ms.keywords: _D3DDDI_QUERYREGISTRY_TYPE, D3DDDI_QUERYREGISTRY_TYPE,
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DDDI_QUERYREGISTRY_TYPE
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- _D3DDDI_QUERYREGISTRY_TYPE
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DDDI_QUERYREGISTRY_TYPE enumeration

## -description
These enumeration values indicate which data to retrieve through QueryAdapterInfo for **KMTQAITYPE_QUERYREGISTRY**.

## -enum-fields

### -field D3DDDI_QUERYREGISTRY_SERVICEKEY
This enumeration value indicates to retrieve registry data from the service hive.
See [Introduction to Registry Keys for Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers) for more details, where it is referred to as the driver's Parameters key.

### -field D3DDDI_QUERYREGISTRY_ADAPTERKEY
This enumeration value indicates to retrieve registry data from the adapter hive.
See [Introduction to Registry Keys for Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers) for more details, where it is referred to as the driver's Software key.

### -field D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH
This enumeration value retrieves the driver store path for the adapter.

### -field D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH
This enumeration value retrieves the driver image path, which includes the driver name associated with [DriverEntry](https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-display-miniport-driver).

### -field D3DDDI_QUERYREGISTRY_MAX
This enum value is invalid to use, and merely exists to simplify maintaining the implementation.

## -see-also
- [D3DDDI_QUERYREGISTRY_INFO](ns-d3dukmdt-_d3dddi_queryregistry_info.md)
