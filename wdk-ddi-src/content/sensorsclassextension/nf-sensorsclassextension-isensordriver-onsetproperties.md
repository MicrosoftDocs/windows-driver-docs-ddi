---
UID: NF:sensorsclassextension.ISensorDriver.OnSetProperties
title: ISensorDriver::OnSetProperties method
author: windows-driver-content
description: The ISensorDriver::OnSetProperties method specifies values for the specified list of properties.
old-location: sensors\isensordriver_onsetproperties.htm
old-project: sensors
ms.assetid: 7c3cca5b-1d08-42dc-8dc4-42eb1160b8bb
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ISensorDriver, ISensorDriver interface [Sensor Devices], OnSetProperties method, ISensorDriver::OnSetProperties, OnSetProperties method [Sensor Devices], OnSetProperties method [Sensor Devices], ISensorDriver interface, OnSetProperties,ISensorDriver.OnSetProperties, Sensor_IFaces_1b27ccef-2b50-4942-b8fa-9126e2624b27.xml, sensors.isensordriver_onsetproperties, sensorsclassextension/ISensorDriver::OnSetProperties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Desktop
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
api_name:
-	ISensorDriver.OnSetProperties
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorDriver::OnSetProperties method


## -description


The <b>ISensorDriver::OnSetProperties</b> method specifies values for the specified list of properties.


## -parameters




### -param pClientFile [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface that represents the file object for the application specifying property values.


### -param pwszSensorID [in]

<b>LPWSTR</b> that contains the ID for the sensor for which the client application is specifying property values.


### -param pPropertiesToSet [in]

Pointer to an <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> interface that contains the list of properties to set and their values.


### -param ppResults [out]

Address of an <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> pointer that receives the list of properties that have been set successfully and their new values. If a property was not set, the new value contains an HRESULT error code.


## -returns



If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Properties describe the sensor device, as opposed to data fields, which contain sensor-generated data.  Platform-defined properties are defined in sensors.h.

The list of properties provided through <i>pPropertiesToSet</i> is typically  a subset of the list you returned through <a href="https://msdn.microsoft.com/library/windows/hardware/ff545630">ISensorDriver::OnGetSupportedProperties</a>. However, the sensor class extension does not enforce this condition on client applications.

The sensor class extension is responsible for freeing any <b>PROPVARIANT</b> structures returned by this method.

<a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> is documented in Windows Portable Devices.

<div class="alert"><b>Note</b>  This method will be called only if the user has enabled the sensor in the <b>Location and Other Sensors</b> control panel.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545610">ISensorDriver::OnGetProperties</a>
 

 

