---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedEvents
title: ISensorDriver::OnGetSupportedEvents method
author: windows-driver-content
description: The ISensorDriver::OnGetSupportedEvents method retrieves the list of events that the specified sensor can raise.
old-location: sensors\isensordriver_ongetsupportedevents.htm
old-project: sensors
ms.assetid: b323f803-56fb-44db-9b88-be25062c08ff
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ISensorDriver, ISensorDriver::OnGetSupportedEvents, OnGetSupportedEvents method [Sensor Devices], OnGetSupportedEvents,ISensorDriver.OnGetSupportedEvents, sensors.isensordriver_ongetsupportedevents
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
-	OnGetSupportedEvents
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorDriver::OnGetSupportedEvents method


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545623">ISensorDriver::OnGetSupportedEvents</a> method retrieves the list of events that the specified sensor can raise.


## -syntax


````
HRESULT OnGetSupportedEvents(
   LPWSTR  pwszSensorID,
   GUID ** ppSupportedEvents,
   ULONG * pulEventCount
);
````


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



