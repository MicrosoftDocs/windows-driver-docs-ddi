---
UID: NF:sensorsclassextension.ISensorClassExtension.PostEvent
title: ISensorClassExtension::PostEvent method
author: windows-driver-content
description: The ISensorClassExtension::PostEvent method raises one or more driver events in the sensor class extension.
old-location: sensors\isensorclassextension_postevent.htm
old-project: sensors
ms.assetid: 201a4558-8755-4a28-9982-c02ce5b5d8e7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorClassExtension, ISensorClassExtension::PostEvent, PostEvent
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
req.alt-api: PostEvent
req.alt-loc: SensorsClassExtension.lib,SensorsClassExtension.dll
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
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorClassExtension::PostEvent method



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545519">ISensorClassExtension::PostEvent</a> method raises one or more driver events in the sensor class extension.



## -syntax

````
HRESULT PostEvent(
   LPWSTR                            pwszSensorID,
   IPortableDeviceValuesCollection * pEventCollection
);
````


## -parameters

### -param pwszSensorID 

LPWSTR that contains the ID for the sensor for which the driver is raising the event.


### -param pEventCollection 

Pointer to an IPortableDeviceValuesCollection interface that contains the list of events being posted and their associated data.


## -returns
This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method succeeded, but no client programs are currently subscribed to events. Do not post events when no clients are subscribed.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The event collection was empty.
<dl>
<dt><b>E_POINTER</b></dt>
</dl>A required pointer argument was <b>NULL</b>.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)</b></dt>
</dl>The class extension is not initialized.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_INTERNAL_DB_CORRUPTION</b></dt>
</dl>A serialization error occurred.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_OBJECT_NOT_FOUND)</b></dt>
</dl>No client programs are currently subscribed to events. Do not post events when no clients are subscribed.

 


## -remarks
The sensor class extension forwards these events to the Sensor API and Location API, which in turn, raise events in client programs.

The collection passed through <i>pEventCollection</i> can contain one or more events. Represent each event and its associated data by using one <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> object. Platform-defined <b>PROPERTYKEY</b>s for events and data types are defined in sensors.h.

Each <a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> object returned by this method must contain a time stamp, as described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545725">SENSOR_CATEGORY_ALL</a>.

The sensor class extension is responsible for freeing any <b>PROPVARIANT</b> structures provided by this method.

To specify the event type, use the SENSOR_EVENT_PARAMETER_EVENT_ID <b>PROPERTYKEY</b> with the appropriate <b>GUID</b> value. 

For an example of a class that creates an event thread, see <a href="https://msdn.microsoft.com/a6e428f8-1613-4e8d-813d-5a54824dab82">Raising sensor events</a>


<a href="http://go.microsoft.com/fwlink/p/?linkid=131486">IPortableDeviceValues</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=131487">IPortableDeviceValuesCollection</a> are documented in Windows Portable Devices.

Raise state change events by calling <a href="https://msdn.microsoft.com/ae3bc846-df63-4186-9554-f4600e1f2066">ISensorClassExtension::PostStateChange</a>.</p>