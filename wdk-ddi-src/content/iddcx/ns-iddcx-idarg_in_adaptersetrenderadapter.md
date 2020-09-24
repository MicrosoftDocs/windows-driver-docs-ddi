---
UID: NS:iddcx.IDARG_IN_ADAPTERSETRENDERADAPTER
title: IDARG_IN_ADAPTERSETRENDERADAPTER
author: windows-driver-content
description: The LUID of the render adapter that the driver would like to be used to rendered the desktop image for the swapchains on this adapter.
tech.root: display
ms.assetid: 8d2d633e-ca83-4114-9a28-b194701bd9d9
ms.author: windowsdriverdev
ms.date: 09/24/2020
keywords: ["IDARG_IN_ADAPTERSETRENDERADAPTER structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: IDARG_IN_ADAPTERSETRENDERADAPTER, ,
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
ms.custom: 19H1
f1_keywords:
 - IDARG_IN_ADAPTERSETRENDERADAPTER
 - iddcx/IDARG_IN_ADAPTERSETRENDERADAPTER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_ADAPTERSETRENDERADAPTER
product:
 - Windows
dev_langs:
 - c++
---

# IDARG_IN_ADAPTERSETRENDERADAPTER structure

## -description

The IDARG_IN_ADAPTERSETRENDERADAPTER structure identifies the render adapter that the driver wants to be used to render the desktop image for the swapchains on this adapter.

## -struct-fields

### -field PreferredRenderAdapter

Locally unique identifier (LUID) that identifies the driver's preferred adapter. Setting a value of {0, 0} indicates that the driver has no preference for the render adapter used.

## -remarks

The driver's specified adapter is a preference and the OS might decide to use a different render adapter. For example, if the specified adapter has been PnpStopped then the OS will pick an alternative.

## -see-also

[**IddCxAdapterSetRenderAdapter**](nf-iddcx-iddcxadaptersetrenderadapter.md)

[**PFN_IDDCXADAPTERSETRENDERADAPTER**](nc-iddcx-pfn_iddcxadaptersetrenderadapter.md)
