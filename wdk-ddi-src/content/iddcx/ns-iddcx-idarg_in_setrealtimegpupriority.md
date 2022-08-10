---
UID: NS:iddcx.IDARG_IN_SETREALTIMEGPUPRIORITY
tech.root: display
title: IDARG_IN_SETREALTIMEGPUPRIORITY
ms.date: 08/09/2022
targetos: Windows
description: Learn more about the IDARG_IN_SETREALTIMEGPUPRIORITY structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_SETREALTIMEGPUPRIORITY
f1_keywords:
 - IDARG_IN_SETREALTIMEGPUPRIORITY
 - iddcx/IDARG_IN_SETREALTIMEGPUPRIORITY
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_SETREALTIMEGPUPRIORITY
---

## -description

A **IDARG_IN_SETREALTIMEGPUPRIORITY** structure is passed to [**IddCxSetRealtimeGPUPriority**](nf-iddcx-iddcxsetrealtimegpupriority.md) when an indirect display driver requests a bump in GPU priority.

## -struct-fields

### -field pDevice

[in] Pointer to an [**IDXGIDevice**](/windows/win32/api/dxgi/nn-dxgi-idxgidevice) interface for the DXGI device that the caller is requesting realtime GPU priority for.

## -see-also

[**IddCxSetRealtimeGPUPriority**](nf-iddcx-iddcxsetrealtimegpupriority.md)

[**IDXGIDevice**](/windows/win32/api/dxgi/nn-dxgi-idxgidevice)
