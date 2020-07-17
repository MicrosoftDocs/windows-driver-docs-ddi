---
UID: NF:sensorsclassextension.ISensorDriver.OnClientSubscribeToEvents
title: ISensorDriver::OnClientSubscribeToEvents (sensorsclassextension.h)
description: The ISensorDriver::OnClientSubscribeToEvents method notifies the sensor driver that an authorized client application is requesting event notifications.
old-location: sensors\isensordriver_onclientsubscribetoevents.htm
tech.root: sensors
ms.assetid: b0528932-d7a8-46d7-bd94-6fd729a9d7f2
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnClientSubscribeToEvents"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnClientSubscribeToEvents method, ISensorDriver.OnClientSubscribeToEvents, ISensorDriver::OnClientSubscribeToEvents, OnClientSubscribeToEvents, OnClientSubscribeToEvents method [Sensor Devices], OnClientSubscribeToEvents method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_onclientsubscribetoevents, sensorsclassextension/ISensorDriver::OnClientSubscribeToEvents
f1_keywords:
 - "sensorsclassextension/OnClientSubscribeToEvents"
 - "OnClientSubscribeToEvents"
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
- OnClientSubscribeToEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorDriver::OnClientSubscribeToEvents


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientsubscribetoevents">ISensorDriver::OnClientSubscribeToEvents</a> method notifies the sensor driver that an authorized client application is requesting event notifications.


## -parameters




### -param pClientFile

Pointer to an IWDFFile interface that represents the file object for the application requesting event notifications.


### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting event notifications.


## -returns



If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



When a client application requests event notifications, the driver raises all events to the sensor class extension for the specified object ID. The class extension then forwards these events to the Sensor API as event notifications for applications. 

You can maintain a reference count of connected applications for each sensor to avoid making event callbacks when not required. 

Platform-defined events are defined in sensors.h.

For more information about how to use this method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/filtering-data">Filtering data</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>
 

 

