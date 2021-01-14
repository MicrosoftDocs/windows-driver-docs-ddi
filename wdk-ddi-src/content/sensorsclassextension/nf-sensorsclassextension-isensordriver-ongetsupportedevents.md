---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedEvents
title: ISensorDriver::OnGetSupportedEvents (sensorsclassextension.h)
description: The ISensorDriver::OnGetSupportedEvents method retrieves the list of events that the specified sensor can raise.
old-location: sensors\isensordriver_ongetsupportedevents.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnGetSupportedEvents"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetSupportedEvents method, ISensorDriver.OnGetSupportedEvents, ISensorDriver::OnGetSupportedEvents, OnGetSupportedEvents, OnGetSupportedEvents method [Sensor Devices], OnGetSupportedEvents method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetsupportedevents, sensorsclassextension/ISensorDriver::OnGetSupportedEvents
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
 - ISensorDriver::OnGetSupportedEvents
 - sensorsclassextension/ISensorDriver::OnGetSupportedEvents
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - ISensorDriver::OnGetSupportedEvents
---

# ISensorDriver::OnGetSupportedEvents


## -description

The <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupportedevents">ISensorDriver::OnGetSupportedEvents</a> method retrieves the list of events that the specified sensor can raise.

## -parameters

### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting the events list.

### -param ppSupportedEvents

Address of a GUID pointer that receives the array of supported event IDs. If the driver does not support events, return a buffer containing a single GUID that has its value set to GUID_NULL.

### -param pulEventCount

Address of a ULONG that receives the count of event IDs in the buffer returned through ppSupportedEvents. If the driver does not support events, set this value to zero.

## -returns

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

Event IDs are represented by <b>GUID</b>s. Platform-defined events are defined in sensors.h. 

You must use CoTaskMemAlloc to create the event ID buffer. The sensor class extension frees this memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>

