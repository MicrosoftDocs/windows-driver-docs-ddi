---
UID: NS:sensorsdef.SENSOR_PROPERTY_LIST
title: SENSOR_PROPERTY_LIST
author: windows-driver-content
description: This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile.
old-location: sensors\sensor_property_list.htm
old-project: sensors
ms.assetid: 03E03BB9-95DB-49C0-AF14-FFF1998C98A7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_PROPERTY_LIST, *PSENSOR_PROPERTY_LIST, SENSOR_PROPERTY_LIST
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
req.alt-api: SENSOR_PROPERTY_LIST
req.alt-loc: Sensorsdef.h
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
req.typenames: *PSENSOR_PROPERTY_LIST, SENSOR_PROPERTY_LIST
req.product: Windows 10 or later.
---

# SENSOR_PROPERTY_LIST structure



## -description
This structure contains a list of all <a href="..\sensorsdef\ns-sensorsdef-sensor_value_pair.md">SENSOR_VALUE_PAIR</a> structures for each sensor. This structure is returned by calling ReadFile.



## -syntax

````
typedef struct _SENSOR_PROPERTY_LIST {
  ULONG       AllocatedSizeInBytes;
  ULONG       Count;
  PROPERTYKEY List[1];
} SENSOR_PROPERTY_LIST, *PSENSOR_PROPERTY_LIST;
````


## -struct-fields

### -field AllocatedSizeInBytes

Represents the number of elements allocated in List.


### -field Count

Represents the number of used entries in List.


### -field List

A list of PROPERTYKEY values.


## -remarks
Note that the <i>List[1]</i> parameter is a variable-sized buffer. The first element is a place-holder and may not accurately the buffer size.

The SENSOR_COLLECTION_LIST structure works with the following helper functions:</p>