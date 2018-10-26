---
UID: NS:sensorsdef.SENSOR_PROPERTY_LIST
title: SENSOR_PROPERTY_LIST
author: windows-driver-content
description: This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile.
old-location: sensors\sensor_property_list.htm
tech.root: sensors
ms.assetid: 03E03BB9-95DB-49C0-AF14-FFF1998C98A7
ms.date: 05/03/2018
ms.keywords: "*PSENSOR_PROPERTY_LIST, PSENSOR_PROPERTY_LIST, PSENSOR_PROPERTY_LIST structure pointer [Sensor Devices], SENSOR_PROPERTY_LIST, SENSOR_PROPERTY_LIST structure [Sensor Devices], sensors.sensor_property_list, sensorsdef/PSENSOR_PROPERTY_LIST, sensorsdef/SENSOR_PROPERTY_LIST"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Sensorsdef.h
api_name:
-	SENSOR_PROPERTY_LIST
product:
- Windows
targetos: Windows
req.typenames: SENSOR_PROPERTY_LIST, *PSENSOR_PROPERTY_LIST
---

# SENSOR_PROPERTY_LIST structure


## -description


This structure contains a list of all <a href="https://msdn.microsoft.com/library/windows/hardware/dn946708">SENSOR_VALUE_PAIR</a> structures for each sensor. This structure is returned by calling ReadFile.


## -struct-fields




### -field AllocatedSizeInBytes

Represents the number of elements allocated in List.


### -field Count

Represents the number of used entries in List.


### -field List

A list of PROPERTYKEY values.


## -remarks



Note that the <i>List[1]</i> parameter is a variable-sized buffer. The first element is a place-holder and may not accurately the buffer size.

The SENSOR_COLLECTION_LIST structure works with the following helper functions:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn957094">SENSOR_COLLECTION_LIST_INIT</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn957095">SENSOR_COLLECTION_LIST_SIZE</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn957093">SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT</a>
</li>
</ul>


