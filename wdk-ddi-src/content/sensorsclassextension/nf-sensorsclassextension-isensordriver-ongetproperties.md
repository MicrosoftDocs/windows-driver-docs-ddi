---
UID: NF:sensorsclassextension.ISensorDriver.OnGetProperties
title: ISensorDriver::OnGetProperties method
author: windows-driver-content
description: The ISensorDriver::OnGetProperties method retrieves values for the specified properties from the specified sensor.
old-location: sensors\isensordriver_ongetproperties.htm
old-project: sensors
ms.assetid: 8c7f378c-b4e6-4074-8b6a-571068b5ab80
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver::OnGetProperties, OnGetProperties method [Sensor Devices], sensors.isensordriver_ongetproperties, ISensorDriver, OnGetProperties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
apiname: 
-	OnGetProperties
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorDriver::OnGetProperties method


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a> method retrieves values for the specified properties from the specified sensor.


## -syntax


````
HRESULT OnGetProperties(
   IWDFFile *                     pClientFile,
   LPWSTR                         pwszSensorID,
   IPortableDeviceKeyCollection * pProperties,
   IPortableDeviceValues **       ppPropertyValues
);
````


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
</ul>Each <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> object returned in this collection must contain values for the required properties, as described in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor Properties</a> reference section.

The sensor class extension is responsible for freeing any <b>PROPVARIANT</b> structures returned by this method.

Sensor properties must not contain information that can be used to identify the user. For more information about user privacy, see <a href="https://msdn.microsoft.com/9defb163-4de6-46cc-b817-d3e6291137be">Privacy and Security in the Sensor and Location Platform</a>.

<a href="http://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> are documented in Windows Portable Devices.


