---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_SIZE
title: SENSOR_COLLECTION_LIST_SIZE function (sensorsdef.h)
description: This function returns the size of a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_size.htm
tech.root: sensors
ms.assetid: 98191F02-E047-41BC-922F-867DED522E59
ms.date: 05/03/2018
keywords: ["SENSOR_COLLECTION_LIST_SIZE function"]
ms.keywords: SENSOR_COLLECTION_LIST_SIZE, SENSOR_COLLECTION_LIST_SIZE function [Sensor Devices], sensors.sensor_collection_list_size, sensorsdef/SENSOR_COLLECTION_LIST_SIZE
f1_keywords:
 - "sensorsdef/SENSOR_COLLECTION_LIST_SIZE"
 - "SENSOR_COLLECTION_LIST_SIZE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Sensorsdef.h
api_name:
- SENSOR_COLLECTION_LIST_SIZE
targetos: Windows
req.typenames: 
---

# SENSOR_COLLECTION_LIST_SIZE function


## -description


This function returns the size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a> structure. 


## -parameters




### -param Count [in]

The number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_value_pair">SENSOR_VALUE_PAIR</a> elements in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>.


## -returns



The <b>SENSOR_COLLECTION_LIST_SIZE</b> function returns a ULONG value that represents the size of the list of sensor-value pairs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>
 

 

