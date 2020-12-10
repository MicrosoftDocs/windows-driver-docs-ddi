---
UID: NS:iddcx.IDARG_IN_GETMOVEREGIONS
title: IDARG_IN_GETMOVEREGIONS (iddcx.h)
description: Gives information to the OS about move regions.
old-location: display\idarg_in_getmoveregions.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IDARG_IN_GETMOVEREGIONS structure"]
ms.keywords: IDARG_IN_GETMOVEREGIONS, IDARG_IN_GETMOVEREGIONS structure [Display Devices], display.idarg_in_getmoveregions, iddcx/IDARG_IN_GETMOVEREGIONS
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
 - IDARG_IN_GETMOVEREGIONS
 - iddcx/IDARG_IN_GETMOVEREGIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_GETMOVEREGIONS
---

# IDARG_IN_GETMOVEREGIONS structure


## -description

                 Gives information to the OS about move regions.

## -struct-fields

### -field MoveRegionInCount

                     [in] Number of move regions in the <b>pMoveRegions</b> array

### -field pMoveRegions

                     [out] Pointer to the buffer where the OS can copy the move regions.

