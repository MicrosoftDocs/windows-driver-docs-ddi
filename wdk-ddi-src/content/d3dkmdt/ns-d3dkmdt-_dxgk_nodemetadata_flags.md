---
UID: NS:d3dkmdt._DXGK_NODEMETADATA_FLAGS
title: DXGK_NODEMETADATA_FLAGS (d3dkmdt.h)
description: Learn more about the DXGK_NODEMETADATA_FLAGS structure.
ms.date: 05/22/2023
keywords: ["DXGK_NODEMETADATA_FLAGS structure"]
ms.keywords: _DXGK_NODEMETADATA_FLAGS, DXGK_NODEMETADATA_FLAGS,
req.header: d3dkmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_NODEMETADATA_FLAGS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _DXGK_NODEMETADATA_FLAGS
 - d3dkmdt/_DXGK_NODEMETADATA_FLAGS
 - DXGK_NODEMETADATA_FLAGS
 - d3dkmdt/DXGK_NODEMETADATA_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_NODEMETADATA_FLAGS
 - DXGK_NODEMETADATA_FLAGS
dev_langs:
 - c++
---

# DXGK_NODEMETADATA_FLAGS structure

## -description

The **DXGK_NODEMETADATA_FLAGS** structure describes the capabilities of an engine on a GPU node.

## -struct-fields

### -field ContextSchedulingSupported

The engine supports the context-based scheduling model.

### -field RingBufferFenceRelease

The engine supports ring buffer fence release. Available starting with Windows 10, version 1809.

### -field SupportTrackedWorkload

The engine supports tracked workloads. Available starting with Windows 10, version 1809.

### -field UserModeSubmission

The engine supports user-mode submission. Available starting with Windows 10, version 1809.

### -field MaxInFlightHwQueueBuffers

The maximum number of command buffers submitted by the hardware scheduler to the kernel-mode driver. A value of zero indicates no limit. Available starting with Windows 10, version 1809.

### -field Reserved

Reserved.

### -field Value

An alternative way to access the structure members.

## -see-also

[**DXGK_NODEMETADATA**](ns-d3dkmdt-_dxgk_nodemetadata.md)

[**DXGKARG_GETNODEMETADATA**](ns-d3dkmdt-_dxgk_nodemetadata)

[**DXGKDDI_GETNODEMETADATA**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata.md)
