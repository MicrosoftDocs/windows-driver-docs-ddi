---
UID: NE:sensorsclassextension.__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0002
title: "__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0002"
author: windows-driver-content
description: The SensorConnectionType enumeration type defines values for the SENSOR_CONNECTION_TYPE property.
old-location: sensors\sensorconnectiontype.htm
old-project: sensors
ms.assetid: 63df4f99-ddc2-4a0b-b19b-63390771d529
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: Sensor_Enums_bca4556b-94f3-4213-9daa-3571f403d556.xml, SENSOR_CONNECTION_TYPE_PC_ATTACHED, sensorsclassextension/SENSOR_CONNECTION_TYPE_PC_ATTACHED, __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0002, SensorConnectionType enumeration [Sensor Devices], SensorConnectionType, sensors.sensorconnectiontype, sensorsclassextension/SENSOR_CONNECTION_TYPE_PC_EXTERNAL, sensorsclassextension/SensorConnectionType, SENSOR_CONNECTION_TYPE_PC_EXTERNAL, SENSOR_CONNECTION_TYPE_PC_INTEGRATED, sensorsclassextension/SENSOR_CONNECTION_TYPE_PC_INTEGRATED
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	SensorsClassExtension.h
apiname:
-	SensorConnectionType
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# __MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0002 enumeration


## -description


The <b>SensorConnectionType</b> enumeration type defines values for the <a href="https://msdn.microsoft.com/1BF1568D-A889-4158-9C6D-160D9B06F0DE">SENSOR_CONNECTION_TYPE</a> property.


## -syntax


````
enum SensorConnectionType {
  SENSOR_CONNECTION_TYPE_PC_INTEGRATED  = 0, 
  SENSOR_CONNECTION_TYPE_PC_ATTACHED    = ( SENSOR_CONNECTION_TYPE_PC_INTEGRATED + 1 ), 
  SENSOR_CONNECTION_TYPE_PC_EXTERNAL    = ( SENSOR_CONNECTION_TYPE_PC_ATTACHED + 1 ) 

};
````


## -enum-fields




### -field SENSOR_CONNECTION_TYPE_PC_INTEGRATED

Indicates that the sensor is built into the computer.


### -field SENSOR_CONNECTION_TYPE_PC_ATTACHED

Indicates that the sensor is attached to the computer, such as through a peripheral device.


### -field SENSOR_CONNECTION_TYPE_PC_EXTERNAL

Indicates that the sensor is connected by external means, such as through a network connection.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957027">Enumeration properties</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SensorConnectionType enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

