---
UID: NE:iddcx.IDDCX_PATH_FLAGS
title: IDDCX_PATH_FLAGS (iddcx.h)
description: Indicates the state of the path.
old-location: display\iddcx_path_flags.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_PATH_FLAGS enumeration"]
ms.keywords: IDDCX_PATH_FLAGS, IDDCX_PATH_FLAGS enumeration [Display Devices], IDDCX_PATH_FLAGS_ACTIVE, IDDCX_PATH_FLAGS_CHANGED, IDDCX_PATH_FLAGS_NONE, display.iddcx_path_flags, iddcx/IDDCX_PATH_FLAGS, iddcx/IDDCX_PATH_FLAGS_ACTIVE, iddcx/IDDCX_PATH_FLAGS_CHANGED, iddcx/IDDCX_PATH_FLAGS_NONE
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
 - IDDCX_PATH_FLAGS
 - iddcx/IDDCX_PATH_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_PATH_FLAGS
---

# IDDCX_PATH_FLAGS enumeration

## -description

A bitwise-OR'd **IDDCX_PATH_FLAGS** value indicates the state of the path.

## -enum-fields

### -field IDDCX_PATH_FLAGS_NONE:0

Indicates that an **IDDCX_PATH_FLAGS_NONE** variable has not yet been assigned a meaningful value.

### -field IDDCX_PATH_FLAGS_CHANGED:1

Indicates whether this path has changed.

### -field IDDCX_PATH_FLAGS_ACTIVE:2

Indicates whether this path is active.

## -see-also

[**IDDCX_PATH**](ns-iddcx-iddcx_path.md)
