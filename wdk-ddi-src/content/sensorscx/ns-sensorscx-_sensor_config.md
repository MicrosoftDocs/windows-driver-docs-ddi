---
UID: NS:sensorscx._SENSOR_CONFIG
title: _SENSOR_CONFIG (sensorscx.h)
description: This structure contains information that the sensor driver passes to the class extension about each sensor.
old-location: sensors\sensor_config.htm
tech.root: sensors
ms.assetid: E21E2FEC-8733-4A8A-A0C4-899F10824F9B
ms.date: 05/03/2018
keywords: ["_SENSOR_CONFIG structure"]
ms.keywords: "*PSENSOR_CONFIG, PSENSOR_CONFIG, PSENSOR_CONFIG structure pointer [Sensor Devices], SENSOR_CONFIG, SENSOR_CONFIG structure [Sensor Devices], _SENSOR_CONFIG, sensors.sensor_config, sensorscx/PSENSOR_CONFIG, sensorscx/SENSOR_CONFIG"
f1_keywords:
 - "sensorscx/SENSOR_CONFIG"
 - "SENSOR_CONFIG"
req.header: sensorscx.h
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
- SensorsCx.h
api_name:
- SENSOR_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SENSOR_CONFIG, *PSENSOR_CONFIG
---

# _SENSOR_CONFIG structure


## -description


This structure contains information that the sensor driver passes to the class extension about each sensor.


## -struct-fields




### -field Size

The allocated size of this structure (in bytes).


### -field pEnumerationList

The list of enumerations. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_collection_list">SENSOR_COLLECTION_LIST</a>.


## -remarks



The SENSOR_CONFIG structure works with the following helper function:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorscx/nf-sensorscx-sensor_config_init">SENSOR_CONFIG_INIT</a>
</li>
</ul>


