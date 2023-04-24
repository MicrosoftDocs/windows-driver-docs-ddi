---
UID: NS:d3dkmddi._DXGK_VALIDATESUBMITCOMMANDFLAGS
title: DXGK_VALIDATESUBMITCOMMANDFLAGS (d3dkmddi.h)
description: Learn more about the DXGK_VALIDATESUBMITCOMMANDFLAGS structure.
ms.date: 03/23/2023
keywords: ["DXGK_VALIDATESUBMITCOMMANDFLAGS structure"]
ms.keywords: _DXGK_VALIDATESUBMITCOMMANDFLAGS, DXGK_VALIDATESUBMITCOMMANDFLAGS,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_VALIDATESUBMITCOMMANDFLAGS
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGK_VALIDATESUBMITCOMMANDFLAGS
 - d3dkmddi/_DXGK_VALIDATESUBMITCOMMANDFLAGS
 - DXGK_VALIDATESUBMITCOMMANDFLAGS
 - d3dkmddi/DXGK_VALIDATESUBMITCOMMANDFLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_VALIDATESUBMITCOMMANDFLAGS
 - DXGK_VALIDATESUBMITCOMMANDFLAGS
dev_langs:
 - c++
---

# DXGK_VALIDATESUBMITCOMMANDFLAGS structure

## -description

The **DXGK_VALIDATESUBMITCOMMANDFLAGS** structure contains flags needed to validate a command buffer.

### -field Value

This value is used to operate over the structure members collectively.

## -struct-fields

### -field HardwareQueueSubmission

**HardwareQueueSubmission** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| TRUE  | [**DxgkDdiSubmitCommandToHwQueue**](nc-d3dkmddi-dxgkddi_submitcommandtohwqueue.md) called [**DXGKDDI_VALIDATESUBMITCOMMAND**](nc-d3dkmddi-dxgkddi_validatesubmitcommand.md). |
| FALSE | [**D3DKMTSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md) called **DXGKDDI_VALIDATESUBMITCOMMAND**. |

### -field Reserved

Reserved.

## -remarks

The kernel-mode driver should interpret these flags as needed to validate the command buffer.

## -see-also

[**DXGKARG_VALIDATESUBMITCOMMAND**](ns-d3dkmddi-_dxgkarg_validatesubmitcommand.md)

[**DXGKDDI_VALIDATESUBMITCOMMAND**](nc-d3dkmddi-dxgkddi_validatesubmitcommand.md)
