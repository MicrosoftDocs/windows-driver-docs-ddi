---
UID: NS:sensorsdef.SENSOR_COLLECTION_LIST
title: SENSOR_COLLECTION_LIST
author: windows-driver-content
description: This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile.
old-location: sensors\sensor_collection_list.htm
old-project: sensors
ms.assetid: B842C707-C6E0-4C56-986E-35BFD32F265D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PSENSOR_COLLECTION_LIST, ,, C, E, I, L, N, O, P, PSENSOR_COLLECTION_LIST, PSENSOR_COLLECTION_LIST structure pointer [Sensor Devices], R, S, SENSOR_COLLECTION_LIST, SENSOR_COLLECTION_LIST structure [Sensor Devices], T, _, sensors.sensor_collection_list, sensorsdef/PSENSOR_COLLECTION_LIST, sensorsdef/SENSOR_COLLECTION_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Sensorsdef.h
apiname:
-	SENSOR_COLLECTION_LIST
product: Windows
targetos: Windows
req.typenames: SENSOR_COLLECTION_LIST, *PSENSOR_COLLECTION_LIST
req.product: Windows 10 or later.
---

# SENSOR_COLLECTION_LIST structure


## -description


This structure contains a list of all <a href="..\sensorsdef\ns-sensorsdef-sensor_value_pair.md">SENSOR_VALUE_PAIR</a> structures for each sensor. This structure is returned by calling ReadFile.


## -syntax


````
typedef struct _SENSOR_COLLECTION_LIST {
  ULONG             AllocatedSizeInBytes;
  ULONG             Count;
  SENSOR_VALUE_PAIR List[1];
} SENSOR_COLLECTION_LIST, *PSENSOR_COLLECTION_LIST;
````


## -struct-fields




### -field AllocatedSizeInBytes

Represents the number of elements allocated in List.


### -field Count

Represents the number of used entries in List.


### -field List

A list of <a href="..\sensorsdef\ns-sensorsdef-sensor_value_pair.md">SENSOR_VALUE_PAIR</a> structures.


## -remarks



The SENSOR_COLLECTION_LIST structure works with the following helper functions:

<ul>
<li>
<a href="..\sensorsdef\nf-sensorsdef-sensor_collection_list_init.md">SENSOR_COLLECTION_LIST_INIT</a>
</li>
<li>
<a href="..\sensorsdef\nf-sensorsdef-sensor_collection_list_size.md">SENSOR_COLLECTION_LIST_SIZE</a>
</li>
<li>
<a href="..\sensorsdef\nf-sensorsdef-sensor_collection_list_calculate_max_count.md">SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT</a>
</li>
</ul>


