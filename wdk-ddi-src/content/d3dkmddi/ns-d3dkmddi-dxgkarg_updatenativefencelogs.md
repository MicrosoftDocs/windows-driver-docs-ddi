---
UID: NS:d3dkmddi._DXGKARG_UPDATENATIVEFENCELOGS
tech.root: display
title: DXGKARG_UPDATENATIVEFENCELOGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_UPDATENATIVEFENCELOGS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_UPDATENATIVEFENCELOGS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_UPDATENATIVEFENCELOGS
 - DXGKARG_UPDATENATIVEFENCELOGS
f1_keywords:
 - _DXGKARG_UPDATENATIVEFENCELOGS
 - d3dkmddi/_DXGKARG_UPDATENATIVEFENCELOGS
 - DXGKARG_UPDATENATIVEFENCELOGS
 - d3dkmddi/DXGKARG_UPDATENATIVEFENCELOGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_UPDATENATIVEFENCELOGS
---

# DXGKARG_UPDATENATIVEFENCELOGS structure (d3dkmddi.h)

## -description

**DXGKARG_UPDATENATIVEFENCELOGS** is the input structure for [**DxgkDdiUpdateNativeFenceLogs**](nc-d3dkmddi-dxgkddi_updatenativefencelogs.md).

## -struct-fields

### -field NumberOfQueues

[in] Number of elements in the array that hHWQueue points to.

### -field hHWQueue

[in] Array of KMD handles of HWQueues whose pending native fence log writes (for both wait and signal logs) must be flushed to the OS log buffer.

### -field Flags

[in] A [**DXGKARG_UPDATENATIVEFENCELOGS_FLAGS**](../d3dkmddi/ns-d3dkmddi-dxgkarg_updatenativefencelogs_flags.md) structure that contains flags for the flush.

### -field Reserved[32]

Reserved for system use.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiUpdateNativeFenceLogs**](nc-d3dkmddi-dxgkddi_updatenativefencelogs.md)
