---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedDataFields
title: ISensorDriver::OnGetSupportedDataFields (sensorsclassextension.h)
description: The ISensorDriver::OnGetSupportedDataFields method retrieves the list of data fields that the specified sensor can provide.
old-location: sensors\isensordriver_ongetsupporteddatafields.htm
tech.root: sensors
ms.assetid: 5020212e-9e3f-468f-8f7c-77d70a8f024b
ms.date: 05/03/2018
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetSupportedDataFields method, ISensorDriver.OnGetSupportedDataFields, ISensorDriver::OnGetSupportedDataFields, OnGetSupportedDataFields, OnGetSupportedDataFields method [Sensor Devices], OnGetSupportedDataFields method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetsupporteddatafields, sensorsclassextension/ISensorDriver::OnGetSupportedDataFields
f1_keywords:
 - "sensorsclassextension/OnGetSupportedDataFields"
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
- OnGetSupportedDataFields
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorDriver::OnGetSupportedDataFields


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupporteddatafields">ISensorDriver::OnGetSupportedDataFields</a> method retrieves the list of data fields that the specified sensor can provide.


## -parameters




### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting the data fields list.


### -param ppSupportedDataFields

Address of an IPortableDeviceKeyCollection pointer that receives the list of PROPERTYKEY values that represent the supported data fields.


## -returns



If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Data fields contain sensor-generated data, as opposed to properties, which describe the sensor device. Platform-defined data fields are defined in sensors.h.

All drivers must support SENSOR_DATA_TYPE_TIMESTAMP as a required data field.

<a href="https://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> is documented in Windows Portable Devices.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>
 

 

