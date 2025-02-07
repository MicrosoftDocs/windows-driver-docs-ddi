---
UID: NE:d3dukmdt._D3DDDI_QUERYREGISTRY_STATUS
title: D3DDDI_QUERYREGISTRY_STATUS (d3dukmdt.h)
description: Learn more about the D3DDDI_QUERYREGISTRY_STATUS enumeration.
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
req.typenames: D3DDDI_QUERYREGISTRY_STATUS
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDI_QUERYREGISTRY_STATUS
 - d3dukmdt/_D3DDDI_QUERYREGISTRY_STATUS
 - D3DDDI_QUERYREGISTRY_STATUS
 - d3dukmdt/D3DDDI_QUERYREGISTRY_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_QUERYREGISTRY_STATUS
 - D3DDDI_QUERYREGISTRY_STATUS
---

# D3DDDI_QUERYREGISTRY_STATUS enumeration

## -description

The **D3DDDI_QUERYREGISTRY_STATUS** enumeration contains retrieved status codes via a *QueryAdapterInfo* call for [**KMTQAITYPE_QUERYREGISTRY**](../d3dkmthk/ne-d3dkmthk-_kmtqueryadapterinfotype.md).

## -enum-fields

### -field D3DDDI_QUERYREGISTRY_STATUS_SUCCESS

Indicates full success, and *QueryAdapterInfo* succeeded as well.
All **D3DDDI_QUERYREGISTRY_INFO** fields starting with **Output*Xxx*** and the [**D3DDDI_QUERYREGISTRY_INFO::Status**](ns-d3dukmdt-_d3dddi_queryregistry_info.md) field are updated by *QueryAdapterInfo*.

### -field D3DDDI_QUERYREGISTRY_STATUS_BUFFER_OVERFLOW

**D3DKMT_QUERYADAPTERINFO::PrivateDriverDataSize** wasn't large enough to retrieve all the requested data.
Only **D3DDDI_QUERYREGISTRY_INFO\::OutputValueSize** is updated by *QueryAdapterInfo*, in addition to the **D3DDDI_QUERYREGISTRY_INFO::Status** field.

### -field D3DDDI_QUERYREGISTRY_STATUS_FAIL

An unspecified error occurred, and *QueryAdapterInfo* failed as well.
All other **D3DDDI_QUERYREGISTRY_INFO** fields are left unmodified upon return from QueryAdapterInfo.
Since **D3DDDI_QUERYREGISTRY_INFO** is a variable-sized struct,
**D3DDDI_QUERYREGISTRY_STATUS_FAIL** will reliably occur when **D3DKMT_QUERYADAPTERINFO::PrivateDriverDataSize** is smaller than the size of **D3DDDI_QUERYREGISTRY_INFO**.

### -field D3DDDI_QUERYREGISTRY_STATUS_MAX

**D3DDDI_QUERYREGISTRY_STATUS_MAX** is invalid to use, and exists only to simplify maintaining the implementation.

## -see-also

[**D3DDDI_QUERYREGISTRY_INFO**](ns-d3dukmdt-_d3dddi_queryregistry_info.md)

[**D3DKMT_QUERYADAPTERINFO**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**Pfnd3dddiQueryadapterinfocb2**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md)
