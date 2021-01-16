---
UID: NF:sensorsclassextension.ISensorClassExtension.PostEvent
title: ISensorClassExtension::PostEvent (sensorsclassextension.h)
description: The ISensorClassExtension::PostEvent method raises one or more driver events in the sensor class extension.
old-location: sensors\isensorclassextension_postevent.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["ISensorClassExtension::PostEvent"]
ms.keywords: ISensorClassExtension interface [Sensor Devices],PostEvent method, ISensorClassExtension.PostEvent, ISensorClassExtension::PostEvent, PostEvent, PostEvent method [Sensor Devices], PostEvent method [Sensor Devices],ISensorClassExtension interface, sensors.isensorclassextension_postevent, sensorsclassextension/ISensorClassExtension::PostEvent
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
 - ISensorClassExtension::PostEvent
 - sensorsclassextension/ISensorClassExtension::PostEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - ISensorClassExtension::PostEvent
---

# ISensorClassExtension::PostEvent


## -description

The <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensorclassextension-postevent">ISensorClassExtension::PostEvent</a> method raises one or more driver events in the sensor class extension.

## -parameters

### -param pwszSensorID

LPWSTR that contains the ID for the sensor for which the driver is raising the event.

### -param pEventCollection

Pointer to an IPortableDeviceValuesCollection interface that contains the list of events being posted and their associated data.

## -returns

This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

|Return code|Description|
|--- |--- |
|S_OK|The method succeeded.|
|S_FALSE|The method succeeded, but no client programs are currently subscribed to events. Do not post events when no clients are subscribed.|
|E_INVALIDARG|The event collection was empty.|
|E_POINTER|A required pointer argument was NULL.|
|HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)|The class extension is not initialized.|
|HRESULT_FROM_WIN32(ERROR_INTERNAL_DB_CORRUPTION|A serialization error occurred.|
|HRESULT_FROM_WIN32(ERROR_OBJECT_NOT_FOUND)|No client programs are currently subscribed to events. Do not post events when no clients are subscribed.|

## -remarks

The sensor class extension forwards these events to the Sensor API and Location API, which in turn, raise events in client programs.

The collection passed through <i>pEventCollection</i> can contain one or more events. Represent each event and its associated data by using one <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> object. Platform-defined <b>PROPERTYKEY</b>s for events and data types are defined in sensors.h.

Each <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> object returned by this method must contain a time stamp, as described in <a href="/windows-hardware/drivers/sensors/sensor-category-all">SENSOR_CATEGORY_ALL</a>.

The sensor class extension is responsible for freeing any <b>PROPVARIANT</b> structures provided by this method.

To specify the event type, use the SENSOR_EVENT_PARAMETER_EVENT_ID <b>PROPERTYKEY</b> with the appropriate <b>GUID</b> value. 

For an example of a class that creates an event thread, see <a href="/windows-hardware/drivers/sensors/raising-events">Raising sensor events</a>


<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> and <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevaluescollection">IPortableDeviceValuesCollection</a> are documented in Windows Portable Devices.

<div class="alert"><b>Note</b>  The sensor class extension will call PropVariantClear for PROPVARIANTs that you pass  to the sensor class extension.</div>
<div> </div>
Raise state change events by calling <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensorclassextension-poststatechange">ISensorClassExtension::PostStateChange</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensorclassextension">ISensorClassExtension</a>

