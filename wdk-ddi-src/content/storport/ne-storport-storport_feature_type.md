---
UID: NE:storport._STORPORT_FEATURE_TYPE
title: STORPORT_FEATURE_TYPE
description: The STORPORT_FEATURE_TYPE enum identifies a Storport feature supported by a miniport.
tech.root: storage
ms.date: 05/13/2021
ms.topic: enum
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

The **STORPORT_FEATURE_TYPE** enum identifies a Storport feature supported by a miniport.

## -enum-fields

### -field StorportFeatureBusTypeUnitControl

ScsiUnitQueryBusType control is supported.

### -field StorportFeatureFruIdUnitControl

ScsiUnitQueryFruId control is supported.

### -field StorportFeatureFruIdAdapterControl

ScsiAdapterQueryFruId control is supported.

### -field StorportFeatureSetEventLoggingAdapterControl

ScsiAdapterSetEventLogging control is supported.

### -field StorportFeatureMax

## -remarks

A miniport provides an array of **STORPORT_FEATURE_TYPE** values when it calls [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md).

## -see-also

[**STOR_SET_EVENT_LOGGING**](ns-storport-stor_set_event_logging.md)

[**STOR_FRU_ID_DESCRIPTION**](ns-storport-stor_fru_id_description.md)

[**STOR_UNIT_CONTROL_QUERY_BUS_TYPE**](ns-storport-stor_unit_control_query_bus_type.md)

[**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md)
