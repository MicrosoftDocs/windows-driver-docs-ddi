---
UID: NS:d3dkmddi._DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
tech.root: display
title: DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
ms.date: 05/13/2021
targetos: Windows
description: DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION is the structure used by the DxgkCbLogEtwEvent callback to log an event when its EventGuid parameter is GUID_DXGKDDI_AZURE_TRIAGE_EVENT.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION, *PDXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - PDXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
f1_keywords:
 - _DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - d3dkmddi/_DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - PDXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - d3dkmddi/PDXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
 - d3dkmddi/DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION
dev_langs:
 - c++
---

## -description

**DXGKDDICB_PARTITIONING_EVENT_NOTIFICATION** is the structure used by the [**DxgkCbLogEtwEvent**](../dispmprt/nc-dispmprt-dxgkcb_log_etw_event.md) callback to log an event when its **EventGuid** parameter is GUID_DXGKDDI_AZURE_TRIAGE_EVENT.

## -struct-fields

### -field hAdapter

The adapter handle used by the driver to identify the instance reporting the event.

### -field EventType

a [**DXGIDDI_PARTITIONING_EVENT_TYPE**](ne-d3dkmddi-dxgiddi_partitioning_event_type.md) value that identifies the type of event being reported.

### -field PartitionId

The notification structure is the same as used elsewhere in the GPU Partitioning DDI (for example, [**DXGKDDI_CREATEVIRTUALGPU**](../dispmprt/nc-dispmprt-dxgkddi_createvirtualgpu.md)) and is a number in 0 to (Partitions - 1) when the event refers to something occurring to a virtual function. If the event refers to something occurring in the context of the physical function, it should report ULONG_MAX - 1. To identify events that occur across the entire GPU, it should report ULONG_MAX.

### -field EventDescription

A useful, descriptive string for the driver to identify the meaning of the event. The driver can also use the **EventData*N*** members as additional string information if this is useful.

### -field EventData1

An optional first parameter that contains additional useful data that may help triage the event.

### -field EventData2

An optional second parameter that contains additional useful data that may help triage the event.

### -field EventData3

An optional third parameter that contains additional useful data that may help triage the event.

### -field EventData4

An optional fourth parameter that contains additional useful data that may help triage the event.

### -field EventData5

An optional fifth parameter that contains additional useful data that may help triage the event.

## -remarks

See [**DxgkCbLogEtwEvent**](../dispmprt/nc-dispmprt-dxgkcb_log_etw_event.md) for details.

## -see-also

[**DxgkCbLogEtwEvent**](../dispmprt/nc-dispmprt-dxgkcb_log_etw_event.md)

[**DXGIDDI_PARTITIONING_EVENT_TYPE**](ne-d3dkmddi-dxgiddi_partitioning_event_type.md)
