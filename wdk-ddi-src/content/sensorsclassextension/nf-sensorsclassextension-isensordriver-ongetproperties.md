---
UID: NF:sensorsclassextension.ISensorDriver.OnGetProperties
title: ISensorDriver::OnGetProperties (sensorsclassextension.h)
description: The ISensorDriver::OnGetProperties method retrieves values for the specified properties from the specified sensor.
old-location: sensors\isensordriver_ongetproperties.htm
tech.root: sensors
ms.assetid: 8c7f378c-b4e6-4074-8b6a-571068b5ab80
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnGetProperties"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetProperties method, ISensorDriver.OnGetProperties, ISensorDriver::OnGetProperties, OnGetProperties, OnGetProperties method [Sensor Devices], OnGetProperties method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetproperties, sensorsclassextension/ISensorDriver::OnGetProperties
f1_keywords:
 - "sensorsclassextension/OnGetProperties"
 - "OnGetProperties"
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- SensorsClassExtension.lib
- SensorsClassExtension.dll
api_name:
- OnGetProperties
targetos: Windows
req.typenames: 
---

# ISensorDriver::OnGetProperties


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetproperties">ISensorDriver::OnGetProperties</a> method retrieves values for the specified properties from the specified sensor.


## -parameters




### -param pClientFile

 Pointer to an IWDFFile interface that represents the file object for the application requesting property values.


### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting property values.


### -param pProperties

 Pointer to an IPortableDeviceKeyCollection that contains the list of PROPERTYKEY values that represent the properties being requested. 


### -param ppPropertyValues

Address of an IPortableDeviceValues pointer that receives the requested property values.


## -returns



If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Properties describe the sensor device, as opposed to data fields, which contain sensor-generated data. Platform-defined properties are defined in sensors.h.

Applications can access some sensor property information before the user grants permission for the sensor. These items are limited to the following IDs defined in sensors.h:

<ul>
<li>
Any <b>PROPERTYKEY</b> that starts with "SENSOR_PROPERTY_".

</li>
<li>
Any category <b>GUID</b> that starts with "SENSOR_CATEGORY_".

</li>
</ul>
Each <a href="https://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> object returned in this collection must contain values for the required properties, as described in the <a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/sensor-properties2">Sensor Properties</a> reference section.

The sensor class extension is responsible for freeing any <b>PROPVARIANT</b> structures returned by this method.

Sensor properties must not contain information that can be used to identify the user. For more information about user privacy, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gnss/privacy-and-security-in-the-sensor-and-location-platform">Privacy and Security in the Sensor and Location Platform</a>.

<a href="https://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> are documented in Windows Portable Devices.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>
 

 

