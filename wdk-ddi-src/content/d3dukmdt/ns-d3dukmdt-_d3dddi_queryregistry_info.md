---
UID: NS:d3dukmdt._D3DDDI_QUERYREGISTRY_INFO
title: _D3DDDI_QUERYREGISTRY_INFO
author: windows-driver-content
description: Contains information about the query registry.
ms.assetid: 946cbde2-3fb2-4974-a446-178c91a81e49
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DDDI_QUERYREGISTRY_INFO, D3DDDI_QUERYREGISTRY_INFO,
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DDDI_QUERYREGISTRY_INFO
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	_D3DDDI_QUERYREGISTRY_INFO
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DDDI_QUERYREGISTRY_INFO structure

## -description
This structure indicates how **D3DKMT_QUERYADAPTERINFO\::pDriverPrivateData** should be reinterpreted when **D3DKMT_QUERYADAPTERINFO\::Type** is **KMTQAITYPE_QUERYREGISTRY**. 
It is used to read the registry for information that is commonly cached during driver installation.

Instead of using raw OS methods, user mode drivers and other components must ubiquitously use this technique on the OS versions where it is supported.
This enables the OS to maximize user mode compatibility with dependency changes and scenarios like virtualized environments.

## -struct-fields

### -field QueryType
*[In] [D3DDDI_QUERYREGISTRY_TYPE](ne-d3dukmdt-_d3dddi_queryregistry_type.md) QueryType*

**QueryType** is the most-significant field.
It indicates whether the registry or file paths are being retrieved, as well as which specific registry hive and file path.

Registry Key Enums:
- **D3DDDI_QUERYREGISTRY_SERVICEKEY**
- **D3DDDI_QUERYREGISTRY_ADAPTERKEY**

File Path Enums:
- **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH**
- **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH**

### -field QueryFlags
*[In] [D3DDDI_QUERYREGISTRY_FLAGS](ns-d3dukmdt-_d3dddi_queryregistry_flags.md) QueryFlags*

**QueryFlags** can do additional operations, like translate retrieved strings containing file paths to the guest environment. 

### -field ValueName
*[In] WCHAR ValueName[ MAX\_PATH ]*

When retrieving registry information, **ValueName** must specify the registry value name to retrieve.
When retrieving file path information, **ValueName** is ignored. 

### -field ValueType
*[In] ULONG ValueType*

When retrieving registry information, **ValueType** must specify the expected registry value type that corresponds to the registry value name.
When retrieving file path information, **ValueType** must be 0 to succeed. 
See [Registry Value Types](https://docs.microsoft.com/en-us/windows/desktop/SysInfo/registry-value-types) for more detail.

### -field PhysicalAdapterIndex
*[In] ULONG PhysicalAdapterIndex*

The physical adapter index in a LDA chain.

### -field OutputValueSize
*[Out] ULONG OutputValueSize*

The size of the output data is retrieved to this field, even when there's wasn't enough room to retrieve that data.
This field is most useful when variable-sized data is being retrieved.

### -field Status
*[Out] [D3DDDI_QUERYREGISTRY_STATUS](ne-d3dukmdt-_d3dddi_queryregistry_status.md) Status*

The status of the query is returned seperately, to indicate varying amounts of data has been retrieved.
The following three return states are most important to understand:
- When QueryAdapterInfo returns STATUS_SUCCESS and **Status** is **D3DDDI_QUERYREGISTRY_STATUS_SUCCESS**, all fields starting with **Output** are valid.
- When QueryAdapterInfo returns STATUS_SUCCESS and **Status** is **D3DDDI_QUERYREGISTRY_STATUS_BUFFER_OVERFLOW**, only **OutputValueSize** is valid.
- When QueryAdapterInfo doesn't return STATUS_SUCCESS, all fields are left unmodified, except **Status** may be changed to **D3DDDI_QUERYREGISTRY_STATUS_FAIL**.

### OutputDword
*[Out] DWORD OutputDword*

**OutputDword** is a convenience field for reinterpreting the successfully retrieved data.
It is most useful when a registry dword is being read.

### OutputQword
*[Out] UINT64 OutputQword*

**OutputQword** is a convenience field for reinterpreting the successfully retrieved data.
It is most useful when a registry qword is being read.

### OutputString
*[Out] WCHAR OutputString[ ANYSIZE\_ARRAY ]*

**OutputString** is a convenience field for reinterpreting the successfully retrieved data.
It is most useful for retreiving a registry string or a file path.

### OutputBinary
*[Out] BYTE OutputBinary[ ANYSIZE\_ARRAY ]*

**OutputBinary** is a convenience field for reinterpreting the successfully retrieved data.
It is most useful when a registry binary blob is being read.

## -see-also
- [D3DDDI_QUERYREGISTRY_TYPE](ne-d3dukmdt-_d3dddi_queryregistry_type.md)
- [D3DDDI_QUERYREGISTRY_FLAGS](ns-d3dukmdt-_d3dddi_queryregistry_flags.md)
- [D3DDDI_QUERYREGISTRY_STATUS](ne-d3dukmdt-_d3dddi_queryregistry_status.md)
- [KMTQUERYADAPTERINFOTYPE](../d3dkmthk/ne-d3dkmthk-_kmtqueryadapterinfotype.md)
- [D3DKMT_QUERYADAPTERINFO](../d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)