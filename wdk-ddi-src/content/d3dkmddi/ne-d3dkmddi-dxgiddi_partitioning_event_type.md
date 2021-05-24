---
UID: NE:d3dkmddi._DXGIDDI_PARTITIONING_EVENT_TYPE
tech.root: display
title: DXGIDDI_PARTITIONING_EVENT_TYPE
ms.date: 05/13/2021
targetos: Windows
description: DXGIDDI_PARTITIONING_EVENT_TYPE identifies the type of ETW event being reported by DxgkCbLogEtwEvent when EventGuid is GUID_DXGKDDI_AZURE_TRIAGE_EVENT.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGIDDI_PARTITIONING_EVENT_TYPE
 - DXGIDDI_PARTITIONING_EVENT_TYPE
f1_keywords:
 - _DXGIDDI_PARTITIONING_EVENT_TYPE
 - d3dkmddi/_DXGIDDI_PARTITIONING_EVENT_TYPE
 - DXGIDDI_PARTITIONING_EVENT_TYPE
 - d3dkmddi/DXGIDDI_PARTITIONING_EVENT_TYPE
dev_langs:
 - c++
---

## -description

**DXGIDDI_PARTITIONING_EVENT_TYPE** identifies the type of ETW event being reported by [**DxgkCbLogEtwEvent**](../dispmprt/nc-dispmprt-dxgkcb_log_etw_event.md) when **EventGuid** is GUID_DXGKDDI_AZURE_TRIAGE_EVENT.

## -enum-fields

### -field DXGK_PARTITION_EVENT_FUNCTION_LEVEL_RESET

A driver specifies this type to indicate a function level reset.

### -field DXGK_PARTITION_EVENT_FUNDAMENTAL_WARM_RESET

A driver specifies this type to indicate a fundamental warm reset.

### -field DXGK_PARTITION_EVENT_DRIVER_INTERNAL

A driver specifies this type to report any unspecified events that may be helpful to issue triage in the field.

## -remarks

See [**DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION**](../d3dkmddi/ns-d3dkmddi-dxgkddicb_partitioning_event_notification.md) for details.

## -see-also

[**DxgkCbLogEtwEvent**](../dispmprt/nc-dispmprt-dxgkcb_log_etw_event.md)
