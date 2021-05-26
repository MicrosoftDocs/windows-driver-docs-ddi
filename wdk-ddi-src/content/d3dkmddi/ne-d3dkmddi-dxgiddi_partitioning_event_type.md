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

A driver specifies this type to indicate a function level reset (FLR). A FLR when the virtual function (VF) must be reset and all register mappings are reset to attempt to unblock a detected timeout. This is typically the first attempted step of an adapter-wide reset on a vGPU in a guest.

### -field DXGK_PARTITION_EVENT_FUNDAMENTAL_WARM_RESET

A driver specifies this type to indicate a fundamental warm reset (FWR). A FWR is the whole-GPU reset that is typically seen on bare metal (non virtualized) adapter resets. A FWR is typically the second and last thing attempted for an adapter reset on a vGPU when the FLR fails to get the adapter executing again. A FWR is disruptive not only to the virtual machine (VM) with the vGPU wanting to be reset, but to all other VMs with assigned vGPUs from that device, so this level of TDR recovery should be avoided wherever possible.

### -field DXGK_PARTITION_EVENT_DRIVER_INTERNAL

A driver specifies this type to report other event(s) with information that might be helpful for issue triage.

## -remarks

**DXGK_PARTITION_EVENT_FUNCTION_LEVEL_RESET** and **DXGK_PARTITION_EVENT_FUNDAMENTAL_WARM_RESET** provide two separate levels of severity when a driver reports timeout detection and recovery (TDR) events.

See [**DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION**](ns-d3dkmddi-dxgkddicb_partitioning_event_notification.md) for additional details.

## -see-also

[**DxgkCbLogEtwEvent**](../dispmprt/nc-dispmprt-dxgkcb_log_etw_event.md)
