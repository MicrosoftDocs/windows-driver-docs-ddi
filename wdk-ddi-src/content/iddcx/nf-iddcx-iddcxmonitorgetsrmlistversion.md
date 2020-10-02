---
UID: NF:iddcx.IddCxMonitorGetSrmListVersion
title: IddCxMonitorGetSrmListVersion
ms.date: 10/02/2020
tech.root: display
ms.assetid: 3c358cd7-558c-4f17-88e8-393b437ab543
ms.topic: language-reference
targetos: Windows
description: IddCxMonitorGetSrmListVersion retrieves the latest System Renewability Message (SRM) list information stored by the GPU.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - iddcx.h
api_name:
 - IddCxMonitorGetSrmListVersion
f1_keywords:
 - iddcx/IddCxMonitorGetSrmListVersion
dev_langs:
 - c++
---

## -description

**IddCxMonitorGetSrmListVersion** retrieves the latest System Renewability Message (SRM) list information stored by the GPU.

## -parameters

### -param MonitorObject

[in] The [IDDCX_MONITOR](/windows-hardware/drivers/display/iddcx-objects) object that the SRM list is associated with.

### -param pInArgs

[in] Pointer to an [IDARG_IN_GETSRMLISTVERSION](ns-iddcx-idarg_in_getsrmlistversion.md) structure with input parameters.

### -param pOutArgs

[out] Pointer to an [IDARG_OUT_GETSRMLISTVERSION](ns-iddcx-idarg_out_getsrmlistversion.md) structure in which the OS returns output.

## -returns

## -remarks

WORK IN PROGRESS

IS THIS RIGHT??? Probably not

Register your implementation of this callback function by setting the appropriate member of IDARG_IN_GETSRMLISTVERSION and then calling IddCxMonitorGetSrmListVersion.


## -see-also

