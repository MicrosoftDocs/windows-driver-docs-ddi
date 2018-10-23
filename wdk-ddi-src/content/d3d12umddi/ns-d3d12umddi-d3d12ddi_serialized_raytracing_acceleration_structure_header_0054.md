---
UID: NS:d3d12umddi.D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054
title: D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054
author: windows-driver-content
description: Describes the header for a serialized ray tracing acceleration structure.
ms.assetid: a71bb18f-181d-4fd2-a8fa-b411d20440ac
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054, D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054 structure

## -description

Describes the header for a serialized ray tracing acceleration structure.

## -struct-fields

### -field DriverMatchingIdentifier

A [D3D12DDI_SERIALIZED_DATA_DRIVER_MATCHING_IDENTIFIER_0054](ns-d3d12umddi-d3d12ddi_serialized_data_driver_matching_identifier_0054.md) structure.

### -field SerializedSizeInBytesIncludingHeader

Size of the serialized acceleration structure, including a header.

### -field DeserializedSizeInBytes

Size of the deserialized acceleration structure, in bytes.

### -field NumBottomLevelAccelerationStructurePointersAfterHeader
 
A 64-byte number of bottom-level acceleration structure pointers.

## -remarks

## -see-also
