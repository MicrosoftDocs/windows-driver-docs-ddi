---
UID: NE:sensorsclassextension.__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001
title: __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001
author: windows-driver-content
description: The SensorState enumeration type specifies the current operational state of a sensor.
old-location: sensors\sensorstate.htm
old-project: sensors
ms.assetid: 5643cb45-daa0-490e-aa0c-9e3b54c6dbef
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_STATE_READY, SENSOR_STATE_NOT_AVAILABLE, SENSOR_STATE_ERROR, Sensor_Enums_caba27ac-659e-4b9a-a466-7a7d202c6f62.xml, sensorsclassextension/SensorState, sensorsclassextension/SENSOR_STATE_NOT_AVAILABLE, sensorsclassextension/SENSOR_STATE_MAX, SensorState, SensorState enumeration [Sensor Devices], SENSOR_STATE_ACCESS_DENIED, SENSOR_STATE_INITIALIZING, SENSOR_STATE_MIN, sensorsclassextension/SENSOR_STATE_NO_DATA, sensorsclassextension/SENSOR_STATE_ERROR, SENSOR_STATE_NO_DATA, sensors.sensorstate, SENSOR_STATE_MAX, sensorsclassextension/SENSOR_STATE_MIN, sensorsclassextension/SENSOR_STATE_ACCESS_DENIED, sensorsclassextension/SENSOR_STATE_INITIALIZING, sensorsclassextension/SENSOR_STATE_READY, __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: <= PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	SensorsClassExtension.h
apiname: 
-	SensorState
product: Windows
targetos: Windows
req.typenames: SensorState
req.product: Windows 10 or later.
---

# __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001 enumeration


## -description


The <b>SensorState</b> enumeration type specifies the current operational state of a sensor.


## -syntax


````
enum SensorState {
  SENSOR_STATE_MIN            = 0, 
  SENSOR_STATE_READY          = SENSOR_STATE_MIN, 
  SENSOR_STATE_NOT_AVAILABLE  = ( SENSOR_STATE_READY + 1 ), 
  SENSOR_STATE_NO_DATA        = ( SENSOR_STATE_NOT_AVAILABLE + 1 ), 
  SENSOR_STATE_INITIALIZING   = ( SENSOR_STATE_NO_DATA + 1 ), 
  SENSOR_STATE_ACCESS_DENIED  = ( SENSOR_STATE_INITIALIZING + 1 ), 
  SENSOR_STATE_ERROR          = ( SENSOR_STATE_ACCESS_DENIED + 1 ), 
  SENSOR_STATE_MAX            = SENSOR_STATE_ERROR 

};
````


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


This enumeration also defines values used for the <a href="https://msdn.microsoft.com/1BF1568D-A889-4158-9C6D-160D9B06F0DE">SENSOR_PROPERTY_STATE</a> property.



## -see-also

<a href="https://msdn.microsoft.com/ae3bc846-df63-4186-9554-f4600e1f2066">ISensorClassExtension::PostStateChange</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SensorState enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

