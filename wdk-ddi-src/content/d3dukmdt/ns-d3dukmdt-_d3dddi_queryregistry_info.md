---
UID: NS:d3dukmdt._D3DDDI_QUERYREGISTRY_INFO
title: D3DDDI_QUERYREGISTRY_INFO (d3dukmdt.h)
description: Learn more about the D3DDDI_QUERYREGISTRY_INFO structure.
ms.date: 02/06/2025
req.header: d3dukmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DDDI_QUERYREGISTRY_INFO
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDI_QUERYREGISTRY_INFO
 - d3dukmdt/_D3DDDI_QUERYREGISTRY_INFO
 - D3DDDI_QUERYREGISTRY_INFO
 - d3dukmdt/D3DDDI_QUERYREGISTRY_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_QUERYREGISTRY_INFO
 - D3DDDI_QUERYREGISTRY_INFO
---

# D3DDDI_QUERYREGISTRY_INFO structure

## -description

The **D3DDDI_QUERYREGISTRY_INFO** structure indicates how [**D3DDDICB_QUERYADAPTERINFO2::pDriverPrivateData**](../d3dumddi/ns-d3dumddi-_d3dddicb_queryadapterinfo2.md) should be reinterpreted when **D3DDDICB_QUERYADAPTERINFO2::QueryType** is **D3DDDI_QUERYADAPTERTYPE_QUERYREGISTRY**.

## -struct-fields

### -field QueryType

[in] A [**D3DDDI_QUERYREGISTRY_TYPE**](ne-d3dukmdt-_d3dddi_queryregistry_type.md) value that indicates which data to retrieve.

**D3DDDI_QUERYREGISTRY_INFO::QueryType** is the most significant field of this structure. It indicates whether the registry or file paths are being retrieved, as well as which specific registry hive and file path.

Registry Key Enums:

* **D3DDDI_QUERYREGISTRY_SERVICEKEY**
* **D3DDDI_QUERYREGISTRY_ADAPTERKEY**

File Path Enums:

* **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH**
* **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH**

### -field QueryFlags

[in] A [**D3DDDI_QUERYREGISTRY_FLAGS**](ns-d3dukmdt-_d3dddi_queryregistry_flags.md) structure with flags that control how strings are retrieved. **QueryFlags** can do additional operations, like translate retrieved strings containing file paths to the guest environment.

### -field ValueName[MAX_PATH]

[in] Zero-terminated UNICODE string that can contain a sub-key name, which is separated from the actual value name by backslash. For example, **ValueName** could be `SubKey1\ SubKey2\NameOfTheValue`. In this case, `SubKey1\ SubKey2` are the subkeys of the service or software keys.

When retrieving registry information, **ValueName** must specify the registry value name to retrieve. When retrieving file path information, **ValueName** is ignored.

### -field ValueType

[in] When retrieving registry information, **ValueType** must specify the expected registry value type that corresponds to the registry value name. It must be REG_SZ, REG_MULTI_SZ, REG_EXPAND_SZ, REG_BINARY, REG_QWORD, or REG_DWORD.

When retrieving file path information, **ValueType** must be 0 to succeed.

See [Registry Value Types](/windows/win32/sysinfo/registry-value-types) for more detail.

### -field PhysicalAdapterIndex

[in] The physical adapter index in a LDA chain.

### -field OutputValueSize

[out] Size in bytes of the written output if [**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3ddi_queryadapterinfocb2.md) succeeds (**Status** is D3DDDI_QUERYREGISTRY_STATUS_SUCCESS). When **Status** is D3DDDI_QUERYREGISTRY_STATUS_BUFFER_OVERFLOW, **OutputValueSize** is the number of bytes required to hold the output value.

### -field Status

[out] A [**D3DDDI_QUERYREGISTRY_STATUS**](ne-d3dukmdt-_d3dddi_queryregistry_status.md) value that indicates the status of the query.

When a user-mode display driver calls the runtime's [**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3ddi_queryadapterinfocb2.md) function, a call to the [**DxgkDdiQueryAdapterInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function is initiated.

The status of the query is returned separately from the return value in order to indicate that varying amounts of data have been retrieved. The following three return states are the most important to understand:

* When **pfnQueryAdapterInfoCb2** returns STATUS_SUCCESS:
  * If **Status** is **D3DDDI_QUERYREGISTRY_STATUS_SUCCESS**, all fields starting with **Output*Xxx*** are valid.
  * If **Status** is **D3DDDI_QUERYREGISTRY_STATUS_BUFFER_OVERFLOW**, there isn't enough space in the private data to hold the registry value. Only **OutputValueSize** is valid.
* When **pfnQueryAdapterInfoCb2** doesn't return STATUS_SUCCESS, all fields are left unmodified, except **Status** might be changed to **D3DDDI_QUERYREGISTRY_STATUS_FAIL**.

### -field OutputDword

[out] A part of the union that holds the output value. **OutputDword** is a convenience field for reinterpreting the successfully retrieved data when a registry DWORD is being read.

### -field OutputQword

[out] A part of the union that holds the output value. **OutputQword** is a convenience field for reinterpreting the successfully retrieved data when a registry QWORD is being read.

### -field OutputString[1]

[out] A part of the union that holds the output value. **OutputString** is a convenience field for reinterpreting the successfully retrieved data when retrieving a registry string or a file path.

### -field OutputBinary[1]

[out] A part of the union that holds the output value. **OutputBinary** is a convenience field for reinterpreting the successfully retrieved data when a registry binary blob is being read.

## -remarks

**D3DDDI_QUERYREGISTRY_INFO** is used to read the registry for information that is commonly cached during driver installation.

Instead of using raw OS methods, user-mode drivers and other components must ubiquitously use this technique on the OS versions where it is supported. This enables the OS to maximize user-mode compatibility with dependency changes and scenarios like virtualized environments. For more information, see [GPU paravirtualization](/windows-hardware/drivers/display/gpu-paravirtualization).

## -see-also

[**D3DDDI_QUERYREGISTRY_TYPE**](ne-d3dukmdt-_d3dddi_queryregistry_type.md)

[**D3DDDI_QUERYREGISTRY_FLAGS**](ns-d3dukmdt-_d3dddi_queryregistry_flags.md)

[**D3DDDI_QUERYREGISTRY_STATUS**](ne-d3dukmdt-_d3dddi_queryregistry_status.md)

[**KMTQUERYADAPTERINFOTYPE**](../d3dkmthk/ne-d3dkmthk-_kmtqueryadapterinfotype.md)

[**D3DKMT_QUERYADAPTERINFO**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3ddi_queryadapterinfocb2.md)
