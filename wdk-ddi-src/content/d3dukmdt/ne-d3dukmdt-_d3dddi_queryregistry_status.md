---
UID: NE:d3dukmdt._D3DDDI_QUERYREGISTRY_STATUS
title: _D3DDDI_QUERYREGISTRY_STATUS (d3dukmdt.h)
description: Query registry status.
ms.assetid: f7d2e2ff-ba33-4685-82dc-47c9d74b08d0
ms.date: 11/21/2018
keywords: ["_D3DDDI_QUERYREGISTRY_STATUS enumeration"]
f1_keywords:
 - "d3dukmdt/_D3DDDI_QUERYREGISTRY_STATUS"
ms.keywords: _D3DDDI_QUERYREGISTRY_STATUS, D3DDDI_QUERYREGISTRY_STATUS,
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3DDDI_QUERYREGISTRY_STATUS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- _D3DDDI_QUERYREGISTRY_STATUS
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DDDI_QUERYREGISTRY_STATUS enumeration

## -description
These status codes indicate how successfully data was retrieved through QueryAdapterInfo for **KMTQAITYPE_QUERYREGISTRY**.

## -enum-fields

### -field D3DDDI_QUERYREGISTRY_STATUS_SUCCESS
This status code indicates full success, and QueryAdapterInfo succeeded as well.
All **D3DDDI_QUERYREGISTRY_INFO** fields starting with **Output** are updated after returning from QueryAdapterInfo, in addition to the **D3DDDI_QUERYREGISTRY_INFO\::Status** field.

### -field D3DDDI_QUERYREGISTRY_STATUS_BUFFER_OVERFLOW
This status code means **D3DKMT_QUERYADAPTERINFO\::PrivateDriverDataSize** was not large enough to retrieve all the requested data.
Only **D3DDDI_QUERYREGISTRY_INFO\::OutputValueSize** is updated after returning from QueryAdapterInfo, in addition to the **D3DDDI_QUERYREGISTRY_INFO\::Status** field.

### -field D3DDDI_QUERYREGISTRY_STATUS_FAIL
An unspecified error occurred, and QueryAdapterInfo failed as well.
All other **D3DDDI_QUERYREGISTRY_INFO** fields are left unmodified after returning from QueryAdapterInfo.
Since **D3DDDI_QUERYREGISTRY_INFO** is a variable-sized struct,
**D3DDDI_QUERYREGISTRY_STATUS_FAIL** will reliably occur when **D3DKMT_QUERYADAPTERINFO\::PrivateDriverDataSize** is smaller than the size of **D3DDDI_QUERYREGISTRY_INFO**.

### -field D3DDDI_QUERYREGISTRY_STATUS_MAX
**D3DDDI_QUERYREGISTRY_STATUS_MAX** is invalid to use, and merely exists to simplify maintaining the implementation.

## -see-also
- [D3DDDI_QUERYREGISTRY_INFO](ns-d3dukmdt-_d3dddi_queryregistry_info.md)
