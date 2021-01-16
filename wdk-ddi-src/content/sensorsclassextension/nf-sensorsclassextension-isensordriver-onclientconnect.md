---
UID: NF:sensorsclassextension.ISensorDriver.OnClientConnect
title: ISensorDriver::OnClientConnect (sensorsclassextension.h)
description: The ISensorDriver::OnClientConnect method notifies the sensor driver that a client application has connected.
old-location: sensors\isensordriver_onclientconnect.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnClientConnect"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnClientConnect method, ISensorDriver.OnClientConnect, ISensorDriver::OnClientConnect, OnClientConnect, OnClientConnect method [Sensor Devices], OnClientConnect method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_onclientconnect, sensorsclassextension/ISensorDriver::OnClientConnect
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
 - ISensorDriver::OnClientConnect
 - sensorsclassextension/ISensorDriver::OnClientConnect
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - ISensorDriver::OnClientConnect
---

# ISensorDriver::OnClientConnect


## -description

The <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientconnect">ISensorDriver::OnClientConnect</a> method notifies the sensor driver that a client application has connected.

## -parameters

### -param pClientFile

Pointer to an IWDFFile interface that represents the file object for the application requesting the connection.

### -param pwszSensorID

LPWSTR that contains the ID for the sensor to which the client application is connecting.

## -returns

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

The sensor class extension calls this method only if the specified client application has been given permission by the user to access the driver. If the user revokes this permission, the class extension immediately calls <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientdisconnect">ISensorDriver::OnClientDisconnect</a> for the same application/sensor pair.

The class extension always calls this method before calling <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onsetproperties">ISensorDriver::OnSetProperties</a> or <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetdatafields">ISensorDriver::OnGetDataFields</a> for a particular sensor. We recommend that you maintain a reference count of connected applications to help to anticipate when calls to these three methods are possible. If no client applications are connected, you may want to change the behavior of the driver, for example, by taking steps to reduce power consumption.

You can use the pointer value (the address pointed to) provided by <i>pClientFile</i> as a kind of ID to keep track of connected applications. However, you must track these IDs separately for each sensor, not for each device, because the class extension may provide the same pointer value to multiple sensors on the same device.

For more information about how to use this method, see <a href="/windows-hardware/drivers/sensors/filtering-data">Filtering data</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>

