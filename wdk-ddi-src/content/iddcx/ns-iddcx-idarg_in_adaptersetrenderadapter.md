---
UID: NS:iddcx.IDARG_IN_ADAPTERSETRENDERADAPTER
title: IDARG_IN_ADAPTERSETRENDERADAPTER
author: windows-driver-content
description: The LUID of the render adapter that the driver would like to be used to rendered the desktop image for the swapchains on this adapter.
tech.root: display
ms.assetid: 8d2d633e-ca83-4114-9a28-b194701bd9d9
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
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
targetos: Windows
---

# IDARG_IN_ADAPTERSETRENDERADAPTER structure

## -description

The LUID of the render adapter that the driver would like to be used to rendered the desktop image for the swapchains on this adapter.

## -struct-fields

### -field PreferredRenderAdapter
 
Setting a value of {0, 0} indicates that the driver has no preference for the render adapter used. This is a preference and the OS may decide to use a different render adapter. For example, if the specified adapter has been PnpStopped then the OS will pick an alternative.

## -remarks

## -see-also