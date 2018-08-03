---
UID: NS:d3dkmddi._DXGK_FRAMEBUFFERSAVEAREA
title: _DXGK_FRAMEBUFFERSAVEAREA
author: windows-driver-content
description:
ms.assetid: b8036275-799b-424f-889e-a3a25700c69f
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_FRAMEBUFFERSAVEAREA, DXGK_FRAMEBUFFERSAVEAREA,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_FRAMEBUFFERSAVEAREA
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGK_FRAMEBUFFERSAVEAREA
product: 
- Windows
targetos: Windows
---

# _DXGK_FRAMEBUFFERSAVEAREA structure

## -description

The size required by the driver to save the frame buffer reserve area during power transitions.

## -struct-fields

### -field MaximumSize

The maximum size required by the driver to save the frame buffer reserve area during power transitions. This value must be a multiple of PAGE_SIZE.

