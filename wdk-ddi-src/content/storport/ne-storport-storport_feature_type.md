---
UID: NE:storport._STORPORT_FEATURE_TYPE
title: STORPORT_FEATURE_TYPE
description: The STORPORT_FEATURE_TYPE enum identifies a Storport feature supported by a miniport.
tech.root: storage
ms.date: 05/24/2022
ms.keywords: STORPORT_FEATURE_TYPE, STORPORT_FEATURE_TYPE,
req.header: storport.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: STORPORT_FEATURE_TYPE
targetos: Windows
f1_keywords:
 - _STORPORT_FEATURE_TYPE
 - storport/_STORPORT_FEATURE_TYPE
 - STORPORT_FEATURE_TYPE
 - storport/STORPORT_FEATURE_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STORPORT_FEATURE_TYPE
 - STORPORT_FEATURE_TYPE
product:
 - Windows
---

# STORPORT_FEATURE_TYPE enumeration

## -description

The **STORPORT_FEATURE_TYPE** enumeration identifies a Storport feature supported by a miniport.

## -enum-fields

### -field StorportFeatureBusTypeUnitControl

Indicates whether the **ScsiUnitQueryBusType** control operation is supported.

### -field StorportFeatureFruIdUnitControl

Indicates whether the **ScsiUnitQueryFruId** control operation is supported.

### -field StorportFeatureFruIdAdapterControl

Indicates whether the **ScsiAdapterQueryFruId** control operation is supported.

### -field StorportFeatureSetEventLoggingAdapterControl

Indicates whether the **ScsiAdapterSetEventLogging** control operation is supported.

### -field StorportFeatureReportInternalDataUnitControl

Indicates whether the **ScsiUnitReportInternalData** control operation is supported.

## -field StorportFeatureReportInternalDataAdapterControl

Indicates whether the **ScsiAdapterReportInternalData** control operation is supported.

## -field StorportFeatureResetBusSynchronous

Indicates whether the **ScsiAdapterResetBusSynchronous** control operation is supported.

## -field StorportFeaturePostHwInitialize

Indicates whether the **ScsiAdapterPostHwInitialize** control operation is supported.

## -field StorportFeaturePrepareEarlyDumpData

Indicates whether the **ScsiAdapterPrepareEarlyDumpData** control operation is supported.

## -field StorportFeatureRestoreEarlyDumpData

Indicates whether the **ScsiAdapterRestoreEarlyDumpData** control operation is supported.

### -field StorportFeatureMax

Max value for this enumeration.

## -remarks

A miniport provides an array of **STORPORT_FEATURE_TYPE** values when it calls [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md), where each value indicates whether the miniport provides support for a control operation.

Storport specifies the control type when it calls a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine.

## -see-also

[**SCSI_ADAPTER_CONTROL_TYPE**](ne-storport-scsi_adapter_control_type.md)

[**STOR_SET_EVENT_LOGGING**](ns-storport-stor_set_event_logging.md)

[**STOR_FRU_ID_DESCRIPTION**](ns-storport-stor_fru_id_description.md)

[**STOR_UNIT_CONTROL_QUERY_BUS_TYPE**](ns-storport-stor_unit_control_query_bus_type.md)

[**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md)
