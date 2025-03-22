---
UID: NE:d3dukmdt._D3DDDI_NATIVEFENCE_TYPE
tech.root: display
title: D3DDDI_NATIVEFENCE_TYPE
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the D3DDDI_NATIVEFENCE_TYPE enumeration.
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
 - _D3DDDI_NATIVEFENCE_TYPE
 - D3DDDI_NATIVEFENCE_TYPE
f1_keywords:
 - _D3DDDI_NATIVEFENCE_TYPE
 - d3dukmdt/_D3DDDI_NATIVEFENCE_TYPE
 - D3DDDI_NATIVEFENCE_TYPE
 - d3dukmdt/D3DDDI_NATIVEFENCE_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_NATIVEFENCE_TYPE
---

# D3DDDI_NATIVEFENCE_TYPE enumeration (d3dukmdt.h)

## -description

A **D3DDDI_NATIVEFENCE_TYPE** enumeration value specifies the type of native fence that the OS.

## -enum-fields

### -field D3DDDI_NATIVEFENCE_TYPE_DEFAULT:0

Indicates full CPU and GPU interoperability. See [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects) for details. Supported starting in Windows 11, version 22H2 (WDDM 3.2).

### -field D3DDDI_NATIVEFENCE_TYPE_INTRA_GPU:1

Special fence type for engine-to-engine synchronization that doesn't support any CPU access or CPU wait/signal operations. See [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects) for details. Not currently supported.

## -remarks

A **D3DDDI_NATIVEFENCE_TYPE** enumeration value dictates the type of native fence that the OS creates. They differ in functionality, performance characteristics, and storage requirements for **CurrentValue** and **MonitoredValue**.

For detailed information about these differences and about native GPU fences in general, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**D3DDDI_NATIVEFENCEINFO**](ns-d3dukmdt-d3dddi_nativefenceinfo.md)

[**D3DKMTCreateNativeFence**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatenativefence.md)
