---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
title: SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function (sensorsdef.h)
description: This function calculates the number of SENSOR_VALUE_PAIR elements in a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_calculate_max_count.htm
tech.root: sensors
ms.assetid: 56C94717-41FF-44AA-BC99-1ECE4A407A38
ms.date: 05/03/2018
keywords: ["SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function"]
ms.keywords: SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT, SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function [Sensor Devices], sensors.sensor_collection_list_calculate_max_count, sensorsdef/SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
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
 - SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
 - sensorsdef/SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Sensorsdef.h
api_name:
 - SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
---

# SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function


## -description

This function calculates the number of <a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_value_pair">SENSOR_VALUE_PAIR</a> elements in a <a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a> structure.

## -parameters

### -param pCollectionList 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a> structure.

## -returns

The <b>SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT</b> function returns a ULONG value.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>



<a href="/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_value_pair">SENSOR_VALUE_PAIR</a>