---
UID: NC:d3dkmddi.DXGKDDI_SETNATIVEFENCELOGBUFFER
tech.root: display
title: DXGKDDI_SETNATIVEFENCELOGBUFFER
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_SETNATIVEFENCELOGBUFFER function.
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
 - DXGKDDI_SETNATIVEFENCELOGBUFFER
f1_keywords:
 - DXGKDDI_SETNATIVEFENCELOGBUFFER
 - d3dkmddi/DXGKDDI_SETNATIVEFENCELOGBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_SETNATIVEFENCELOGBUFFER
---

# DXGKDDI_SETNATIVEFENCELOGBUFFER function (d3dkmddi.h)

## -description

*Dxgkrnl* calls **DxgkDdiSetNativeFenceLogBuffer** to inform the kernel-mode display miniport driver (KMD) of the location of the specified native fence log buffer.

## -parameters

### -param pSetNativeFenceLogBuffer

[in] Pointer to a [**DXGKARG_SETNATIVEFENCELOGBUFFER**](ns-d3dkmddi-dxgkarg_setnativefencelogbuffer.md) structure that contains the native fence log buffer information.

## -returns

**DxgkDdiSetNativeFenceLogBuffer** returns STATUS_SUCCESS if KMD was able to successfully set the native fence log buffer. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

*Dxgkrnl* can destroy and recreate a log buffer. Each time it does, it calls **DxgkDdiSetNativeFenceLogBuffer** to inform KMD of the new location.

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_SETNATIVEFENCELOGBUFFER**](ns-d3dkmddi-dxgkarg_setnativefencelogbuffer.md)
