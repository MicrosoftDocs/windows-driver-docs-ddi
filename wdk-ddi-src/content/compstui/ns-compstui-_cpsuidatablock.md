---
UID: NS:compstui._CPSUIDATABLOCK
title: CPSUIDATABLOCK (compstui.h)
description: The CPSUIDATABLOCK structure is used as a parameter for the ComPropSheet function, if the function code is CPSFUNC_SET_DATABLOCK or CPSFUNC_QUERY_DATABLOCK.
tech.root: print
ms.date: 11/15/2022
keywords: ["CPSUIDATABLOCK structure"]
ms.keywords: "*PCPSUIDATABLOCK, CPSUIDATABLOCK, CPSUIDATABLOCK structure [Print Devices], PCPSUIDATABLOCK, PCPSUIDATABLOCK structure pointer [Print Devices], _CPSUIDATABLOCK, compstui/CPSUIDATABLOCK, compstui/PCPSUIDATABLOCK, cpsuifnc_c9e406f5-1d6a-403d-a286-89cf199a09d2.xml, print.cpsuidatablock"
req.header: compstui.h
req.include-header: Compstui.h
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
req.typenames: CPSUIDATABLOCK, *PCPSUIDATABLOCK
f1_keywords:
 - _CPSUIDATABLOCK
 - compstui/_CPSUIDATABLOCK
 - PCPSUIDATABLOCK
 - compstui/PCPSUIDATABLOCK
 - CPSUIDATABLOCK
 - compstui/CPSUIDATABLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _CPSUIDATABLOCK
 - PCPSUIDATABLOCK
 - CPSUIDATABLOCK
---

## -description

The **CPSUIDATABLOCK** structure is used as a parameter for the [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function, if the function code is [CPSFUNC_SET_DATABLOCK](/previous-versions/ff547036(v=vs.85)) or [CPSFUNC_QUERY_DATABLOCK](/previous-versions/ff546425(v=vs.85)).

## -struct-fields

### -field cbData

Size, in bytes of the buffer pointed to by **pbData**.

### -field pbData

Pointer to a caller-allocated buffer.
