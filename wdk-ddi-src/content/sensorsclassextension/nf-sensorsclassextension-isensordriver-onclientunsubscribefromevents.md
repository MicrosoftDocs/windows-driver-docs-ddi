---
UID: NF:sensorsclassextension.ISensorDriver.OnClientUnsubscribeFromEvents
title: ISensorDriver::OnClientUnsubscribeFromEvents method
author: windows-driver-content
description: The ISensorDriver::OnClientUnsubscribeFromEvents method notifies the sensor driver that a client application no longer requests event notifications.
old-location: sensors\isensordriver_onclientunsubscribefromevents.htm
old-project: sensors
ms.assetid: f51f1091-232f-4e41-9cc2-9938870aeef8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorDriver, ISensorDriver::OnClientUnsubscribeFromEvents, OnClientUnsubscribeFromEvents
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
req.alt-api: OnClientUnsubscribeFromEvents
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

# ISensorDriver::OnClientUnsubscribeFromEvents method



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545598">ISensorDriver::OnClientUnsubscribeFromEvents</a> method notifies the sensor driver that a client application no longer requests event notifications.



## -syntax

````
HRESULT OnClientUnsubscribeFromEvents(
   IWDFFile * pClientFile,
   LPWSTR     pwszSensorID
);
````


## -parameters

### -param pClientFile 

 Pointer to an IWDFFile interface that represents the file object for the application requesting cancellation of event notifications.


### -param pwszSensorID 

LPWSTR that contains the ID for the sensor from which the client application is requesting cancellation of event notifications.


## -returns
If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
The sensor class extension calls this method in the following instances:

An application unsubscribes from events.

An application closes normally.

The user revokes permission for an application to access the device that contains the specified sensor.

The sensor class extension is shutting down.

The cleanup work from a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545512">ISensorClassExtension::CleanupFile</a> has completed.

You can use this call as a signal to update the reference count of applications requesting events for the specified sensor.

For more information about how to use this method, see <a href="https://msdn.microsoft.com/1895EC5C-08C1-4976-83F2-CD5A2B55338D">Filtering data</a>.

The ClientData structure is defined as follows.</p>