---
UID: NS:iddcx.IDARG_IN_MAXDISPLAYPIPELINERATE
title: IDARG_IN_MAXDISPLAYPIPELINERATE (iddcx.h)
description: Gives information about the maximum display pipeline rate.
old-location: display\idarg_in_maxdisplaypipelinerate.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IDARG_IN_MAXDISPLAYPIPELINERATE structure"]
ms.keywords: IDARG_IN_MAXDISPLAYPIPELINERATE, IDARG_IN_MAXDISPLAYPIPELINERATE structure [Display Devices], display.idarg_in_maxdisplaypipelinerate, iddcx/IDARG_IN_MAXDISPLAYPIPELINERATE
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
 - IDARG_IN_MAXDISPLAYPIPELINERATE
 - iddcx/IDARG_IN_MAXDISPLAYPIPELINERATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_MAXDISPLAYPIPELINERATE
---

# IDARG_IN_MAXDISPLAYPIPELINERATE structure


## -description

                 Gives information about the maximum display pipeline rate.

## -struct-fields

### -field Reason

                     Indicates the reason why the driver is updating the rate.

### -field MaxDisplayPipelineRate

                     Indicates the maximum display pipeline rate. This is the new value for <b>IDDCX_ADAPTER_CAPS.MaxDisplayPipelineRate</b>

