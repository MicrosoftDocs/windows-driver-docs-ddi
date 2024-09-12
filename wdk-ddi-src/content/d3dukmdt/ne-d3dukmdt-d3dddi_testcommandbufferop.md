---
UID: NE:d3dukmdt._D3DDDI_TESTCOMMANDBUFFEROP
tech.root: display
title: D3DDDI_TESTCOMMANDBUFFEROP
ms.date: 06/17/2024
targetos: Windows
description: Learn about the D3DDDI_TESTCOMMANDBUFFEROP enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_TESTCOMMANDBUFFEROP
 - D3DDDI_TESTCOMMANDBUFFEROP
f1_keywords:
 - _D3DDDI_TESTCOMMANDBUFFEROP
 - d3dukmdt/_D3DDDI_TESTCOMMANDBUFFEROP
 - D3DDDI_TESTCOMMANDBUFFEROP
 - d3dukmdt/D3DDDI_TESTCOMMANDBUFFEROP
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_TESTCOMMANDBUFFEROP
---

## -description

A **D3DDDI_TESTCOMMANDBUFFEROP** enumeration specifies the type of operation for a test command buffer.

## -enum-fields

### -field D3DDDI_TESTCOMMANDBUFFEROP_INVALID:0

The operation is invalid or not specified.

### -field D3DDDI_TESTCOMMANDBUFFEROP_COPY:1

The command buffer operation is a copy operation.

### -field D3DDDI_TESTCOMMANDBUFFEROP_FILL:2

The command buffer operation is a fill operation.

### -field D3DDDI_TESTCOMMANDBUFFEROP_INFINITE_LOOP:3

The command is used to simulate a hung engine. The generated infinite loop must be not preemptable.

### -field D3DDDI_TESTCOMMANDBUFFEROP_INFINITE_PREEMPTABLE_LOOP:4

The command is used to test preemption of a long running command. The generated infinite loop must be preemptable.

### -field D3DDDI_TESTCOMMANDBUFFEROP_MAX

Maximum value for this enumeration.

## -remarks

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**D3DDDI_TESTCOMMANDBUFFER**](ns-d3dukmdt-d3dddi_testcommandbuffer.md)

[**pfnBuildTestCommandBuffer**](../d3dkmddi/ns-d3dkmddi-dxgkddi_kernelmodetestinginterface.md)
