---
UID: NS:iddcx.IDARG_IN_QUERYTARGET_INFO
tech.root: display
title: IDARG_IN_QUERYTARGET_INFO
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_QUERYTARGET_INFO structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_QUERYTARGET_INFO
f1_keywords:
 - IDARG_IN_QUERYTARGET_INFO
 - iddcx/IDARG_IN_QUERYTARGET_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_QUERYTARGET_INFO
---

## -description

The **IDARG_IN_QUERYTARGET_INFO** structure contains input arguments for the [**EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO**](nc-iddcx-evt_idd_cx_adapter_query_target_info.md) callback function.

## -struct-fields

### -field ConnectorIndex

The connector index of the target monitor being queried. The driver provided this index in a prior call to [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO**](nc-iddcx-evt_idd_cx_adapter_query_target_info.md)

[**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md)
