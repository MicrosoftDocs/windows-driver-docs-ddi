---
UID: NE:iddcx.IDDCX_DEFAULT_HDR_METADATA_TYPE
tech.root: display
title: IDDCX_DEFAULT_HDR_METADATA_TYPE
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DEFAULT_HDR_METADATA_TYPE enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_DEFAULT_HDR_METADATA_TYPE
f1_keywords:
 - IDDCX_DEFAULT_HDR_METADATA_TYPE
 - iddcx/IDDCX_DEFAULT_HDR_METADATA_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DEFAULT_HDR_METADATA_TYPE
---

## -description

The **IDDCX_DEFAULT_HDR_METADATA_TYPE** enumeration identifies the type of the default metadata.

## -enum-fields

### -field IDDCX_HDRMETADATA_TYPE_UNINITIALIZED:0

Indicates that an **IDDCX_DEFAULT_HDR_METADATA_TYPE** variable has not yet been assigned a meaningful value.

### -field IDDCX_HDRMETADATA_TYPE_HDR10:1

The metadata being referred to is an HDR10 metadata block.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](ns-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md)

[**IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA**](ns-iddcx-idarg_in_monitor_set_default_hdr_metadata.md)
