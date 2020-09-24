---
UID: NS:iddcx.IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE
title: IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE
description: IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE contains the arguments used in the IddCxAdapterDisplayConfigUpdate function.
tech.root: display
ms.assetid: 67a33cad-55df-4e65-9f8a-5e684fad8d6e
ms.author: windowsdriverdev
ms.date: 09/24/2020
keywords: ["IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: 
targetos: Windows
ms.custom: rs6, 19H1
f1_keywords:
 - IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE
 - iddcx/IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE
product:
 - Windows
dev_langs:
 - c++
---

# IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE structure

## -description

**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE** contains the arguments used in the [**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md)
 function.

## -struct-fields

### -field PathCount

[in] The number of paths in the pPaths array. **PathCount** cannot be zero.

### -field pPaths

[in] Pointer to array of [**IDDCX_DISPLAYCONFIGPATH**](ns-iddcx-iddcx_displayconfigpath.md) structures containing path display configuration information.

## -remarks

An indirect display driver (IDD) calls [**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md) when it receives a new display configuration.

## -see-also

[**IDDCX_DISPLAYCONFIGPATH**](ns-iddcx-iddcx_displayconfigpath.md)

[**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md)
