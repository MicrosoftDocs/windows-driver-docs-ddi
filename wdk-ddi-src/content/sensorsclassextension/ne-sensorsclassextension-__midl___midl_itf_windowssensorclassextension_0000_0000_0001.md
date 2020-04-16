---
UID: NE:sensorsclassextension.__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001
title: __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001 (sensorsclassextension.h)
description: The SensorState enumeration type specifies the current operational state of a sensor.
old-location: sensors\sensorstate.htm
tech.root: sensors
ms.assetid: 5643cb45-daa0-490e-aa0c-9e3b54c6dbef
ms.date: 05/03/2018
keywords: ["__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001 enumeration"]
ms.keywords: SENSOR_STATE_ACCESS_DENIED, SENSOR_STATE_ERROR, SENSOR_STATE_INITIALIZING, SENSOR_STATE_MAX, SENSOR_STATE_MIN, SENSOR_STATE_NOT_AVAILABLE, SENSOR_STATE_NO_DATA, SENSOR_STATE_READY, SensorState, SensorState enumeration [Sensor Devices], Sensor_Enums_caba27ac-659e-4b9a-a466-7a7d202c6f62.xml, __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001, sensors.sensorstate, sensorsclassextension/SENSOR_STATE_ACCESS_DENIED, sensorsclassextension/SENSOR_STATE_ERROR, sensorsclassextension/SENSOR_STATE_INITIALIZING, sensorsclassextension/SENSOR_STATE_MAX, sensorsclassextension/SENSOR_STATE_MIN, sensorsclassextension/SENSOR_STATE_NOT_AVAILABLE, sensorsclassextension/SENSOR_STATE_NO_DATA, sensorsclassextension/SENSOR_STATE_READY, sensorsclassextension/SensorState
f1_keywords:
 - "sensorsclassextension/SensorState"
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7,Available in Windows 7.
req.target-min-winversvr: None supported
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
- SensorsClassExtension.h
api_name:
- SensorState
product:
- Windows
targetos: Windows
req.typenames: SensorState
---

# __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001 enumeration


## -description


The <b>SensorState</b> enumeration type specifies the current operational state of a sensor.


## -enum-fields




### -field SENSOR_STATE_MIN

Reserved.


### -field SENSOR_STATE_READY

Indicates that the sensor is ready.


### -field SENSOR_STATE_NOT_AVAILABLE

Indicates that the sensor is not currently available for use.


### -field SENSOR_STATE_NO_DATA

Indicates that no data available.


### -field SENSOR_STATE_INITIALIZING

Indicates that the sensor is not yet ready for use. Try again.


### -field SENSOR_STATE_ACCESS_DENIED

Reserved. Do not use in driver code.


### -field SENSOR_STATE_ERROR

Indicates that an unspecified error occurred.


### -field SENSOR_STATE_MAX

Reserved.


## -remarks



This enumeration also defines values used for the <a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/sensor-properties2">SENSOR_PROPERTY_STATE</a> property.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensorclassextension-poststatechange">ISensorClassExtension::PostStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetproperties">ISensorDriver::OnGetProperties</a>
 

 

