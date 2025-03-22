---
UID: NC:d3dkmddi.DXGKDDI_UPDATENATIVEFENCELOGS
tech.root: display
title: DXGKDDI_UPDATENATIVEFENCELOGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_UPDATENATIVEFENCELOGS function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_UPDATENATIVEFENCELOGS
f1_keywords:
 - DXGKDDI_UPDATENATIVEFENCELOGS
 - d3dkmddi/DXGKDDI_UPDATENATIVEFENCELOGS
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_UPDATENATIVEFENCELOGS
---

# DXGKDDI_UPDATENATIVEFENCELOGS function (d3dkmddi.h)

## -description

**DxgkDdiUpdateNativeFenceLogs** synchronously flushes pending native fence log writes on demand.

## -parameters

### -param pUpdateNativeFenceLog

[in] Pointer to a [**DXGKARG_UPDATENATIVEFENCELOGS**](ns-d3dkmddi-dxgkarg_updatenativefencelogs.md) structure that contains the native fence log information.

## -returns

**DxgkDdiUpdateNativeFenceLogs** returns STATUS_SUCCESS if the flush was successful. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

A native fence log buffer can be read/written to asynchronously. To force a synchronous flush of the log buffer, the KMD can call **DxgkDdiUpdateNativeFenceLogs**.

The KMD should insert a memory barrier to the given HWQueue, which ensures that all log entry writes are committed.

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_UPDATENATIVEFENCELOGS**](ns-d3dkmddi-dxgkarg_updatenativefencelogs.md)

[**DxgkDdiSetNativeFenceLogBuffer**](nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
