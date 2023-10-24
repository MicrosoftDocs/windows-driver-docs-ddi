---
UID: NS:iddcx.IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA
tech.root: display
title: IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA structure.
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
 - IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA
f1_keywords:
 - IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA
 - iddcx/IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA
---

## -description

The **IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA** structure contains the input arguments for the [**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](nc-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md) callback function.

## -struct-fields

### -field Type

An [**IDDCX_DEFAULT_HDR_METADATA_TYPE**](ne-iddcx-iddcx_default_hdr_metadata_type.md) value that identifies the type of the default metadata that **Data** points to.

### -field Size

The size in bytes of the buffer that **Data** points to.

### -field Data

Union with the metadata.

### -field Data.pHdr10

Pointer to an [**IDDCX_HDR10_METADATA**](ns-iddcx-iddcx_hdr10_metadata.md) structure that contains the HDR10 metadata that the driver is to save and use if requested later.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](nc-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md)

[**IDDCX_DEFAULT_HDR_METADATA_TYPE**](ne-iddcx-iddcx_default_hdr_metadata_type.md)

[**IDDCX_HDR10_METADATA**](ns-iddcx-iddcx_hdr10_metadata.md)
