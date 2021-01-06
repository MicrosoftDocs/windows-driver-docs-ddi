---
UID: NF:sensorsclassextension.ISensorDriver.OnGetDataFields
title: ISensorDriver::OnGetDataFields (sensorsclassextension.h)
description: The ISensorDriver::OnGetDataFields method retrieves current sensor data.
old-location: sensors\isensordriver_ongetdatafields.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnGetDataFields"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetDataFields method, ISensorDriver.OnGetDataFields, ISensorDriver::OnGetDataFields, OnGetDataFields, OnGetDataFields method [Sensor Devices], OnGetDataFields method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetdatafields, sensorsclassextension/ISensorDriver::OnGetDataFields
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ISensorDriver::OnGetDataFields
 - sensorsclassextension/ISensorDriver::OnGetDataFields
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - OnGetDataFields
---

# ISensorDriver::OnGetDataFields


## -description

The <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetdatafields">ISensorDriver::OnGetDataFields</a> method retrieves current sensor data.

## -parameters

### -param pClientFile

 Pointer to an IWDFFile interface that represents the file object for the application requesting the data.

### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting data.

### -param pDataFields

Pointer to an IPortableDeviceKeyCollection that contains the list of PROPERTYKEY values that represent the data fields being requested.

### -param ppDataValues

Address of an IPortableDeviceValues pointer that receives the requested data.

## -returns

This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The method succeeded. | 
| **HRESULT_FROM_WIN32(ERROR_NO_DATA)** | The sensor has no data to report. Each of the data fields returned in the ppDataValues parameter is VT_EMPTY. |

## -remarks

Data fields contain sensor-generated data, as opposed to properties, which describe the sensor device. Platform-defined data fields are defined in sensors.h.

Each <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> object returned by this method must contain a time stamp, as described in <a href="/windows-hardware/drivers/sensors/sensor-category-all">SENSOR_CATEGORY_ALL</a>. 

The sensor class extension is responsibile for freeing any <b>PROPVARIANT</b> structures returned by this method.

The sensor class extension calls this method only for sensors for which the user has granted permission through Control Panel.

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection</a> and <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> are documented in Windows Portable Devices.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>
