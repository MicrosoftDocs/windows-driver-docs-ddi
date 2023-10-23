---
UID: NS:iddcx.IDARG_IN_COMMITMODES
title: IDARG_IN_COMMITMODES (iddcx.h)
description: Learn more about the IDARG_IN_COMMITMODES structure.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDARG_IN_COMMITMODES structure"]
ms.keywords: IDARG_IN_COMMITMODES, IDARG_IN_COMMITMODES structure [Display Devices], display.idarg_in_commitmodes, iddcx/IDARG_IN_COMMITMODES
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDARG_IN_COMMITMODES
 - iddcx/IDARG_IN_COMMITMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_COMMITMODES
---

# IDARG_IN_COMMITMODES structure

## -description

The **IDARG_IN_COMMITMODES** structure contains input parameters for the [**EVT_IDD_CX_ADAPTER_COMMIT_MODES**](nc-iddcx-evt_idd_cx_adapter_commit_modes.md) callback function.

## -struct-fields

### -field PathCount

[in] The number of paths in the array that **pPaths** points to.

### -field pPaths

[in] A pointer to the array of [**IDDCX_PATH**](ns-iddcx-iddcx_path.md) structures containing the paths that need to be committed.

## -see-also

[**EVT_IDD_CX_ADAPTER_COMMIT_MODES**](nc-iddcx-evt_idd_cx_adapter_commit_modes.md)

[**IDDCX_PATH**](ns-iddcx-iddcx_path.md)
