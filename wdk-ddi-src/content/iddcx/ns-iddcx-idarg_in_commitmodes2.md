---
UID: NS:iddcx.IDARG_IN_COMMITMODES2
tech.root: display
title: IDARG_IN_COMMITMODES2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_COMMITMODES2 structure.
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
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_COMMITMODES2
f1_keywords:
 - IDARG_IN_COMMITMODES2
 - iddcx/IDARG_IN_COMMITMODES2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_COMMITMODES2
---

## -description

The **IDARG_IN_COMMITMODES2** structure contains input parameters for the [**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md) callback function, which allows a driver to report extra information needed for HDR10 or WCG monitor modes.

## -struct-fields

### -field PathCount

[in] The number of paths in the array pointed to by **pPaths**.

### -field pPaths

[in] Pointer to an array of [**IDDCX_PATH2**](ns-iddcx-iddcx_path2.md) structures that contain the paths that need to be committed.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md)

[**IDDCX_PATH2**](ns-iddcx-iddcx_path2.md)
