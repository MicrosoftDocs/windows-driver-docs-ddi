---
UID: NF:sensorsdef.SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
title: SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function (sensorsdef.h)
description: This function calculates the number of PROPERTYKEY elements.
old-location: sensors\sensor_property_list_calculate_max_count.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function"]
ms.keywords: SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT, SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function [Sensor Devices], sensors.sensor_property_list_calculate_max_count, sensorsdef/SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
req.header: sensorsdef.h
req.include-header: 
req.target-type: Desktop
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
 - SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
 - sensorsdef/SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Sensorsdef.h
api_name:
 - SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
---

# SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function


## -description

This function calculates the number of PROPERTYKEY elements.

## -parameters

### -param pPropertyList [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_property_list">SENSOR_PROPERTY_LIST</a> structure.

## -returns

The <b>SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT</b> function returns a ULONG value that represents the number of PROPERTYKEY elements.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_property_list">SENSOR_PROPERTY_LIST</a>
