---
UID: NS:sensorsdef.SENSOR_COLLECTION_LIST
title: SENSOR_COLLECTION_LIST (sensorsdef.h)
description: This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile.
old-location: sensors\sensor_collection_list.htm
tech.root: sensors
ms.assetid: B842C707-C6E0-4C56-986E-35BFD32F265D
ms.date: 05/03/2018
ms.keywords: "*PSENSOR_COLLECTION_LIST, PSENSOR_COLLECTION_LIST, PSENSOR_COLLECTION_LIST structure pointer [Sensor Devices], SENSOR_COLLECTION_LIST, SENSOR_COLLECTION_LIST structure [Sensor Devices], sensors.sensor_collection_list, sensorsdef/PSENSOR_COLLECTION_LIST, sensorsdef/SENSOR_COLLECTION_LIST"
ms.topic: struct
f1_keywords:
 - "sensorsdef/SENSOR_COLLECTION_LIST"
req.header: sensorsdef.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- SENSOR_COLLECTION_LIST
product:
- Windows
targetos: Windows
req.typenames: SENSOR_COLLECTION_LIST, *PSENSOR_COLLECTION_LIST
---

# SENSOR_COLLECTION_LIST structure


## -description


This structure contains a list of all <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/ns-sensorsdef-sensor_value_pair">SENSOR_VALUE_PAIR</a> structures for each sensor. This structure is returned by calling ReadFile.


## -struct-fields




### -field AllocatedSizeInBytes

Represents the number of elements allocated in List.


### -field Count

Represents the number of used entries in List.


### -field List

A list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/ns-sensorsdef-sensor_value_pair">SENSOR_VALUE_PAIR</a> structures.


## -remarks



The SENSOR_COLLECTION_LIST structure works with the following helper functions:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/nf-sensorsdef-sensor_collection_list_init">SENSOR_COLLECTION_LIST_INIT</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/nf-sensorsdef-sensor_collection_list_size">SENSOR_COLLECTION_LIST_SIZE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sensorsdef/nf-sensorsdef-sensor_collection_list_calculate_max_count">SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT</a>
</li>
</ul>


