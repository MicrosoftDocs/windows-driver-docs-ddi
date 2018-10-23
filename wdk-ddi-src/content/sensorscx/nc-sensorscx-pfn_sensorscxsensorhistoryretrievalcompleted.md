---
UID: NC:sensorscx.PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
title: *PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
author: windows-driver-content
description: Indicates that the history retrieval has completed.
ms.assetid: 62f81ebc-b081-42d6-a757-44d94b1da693
ms.date: 10/19/2018
ms.topic: callback
req.header: sensorscx.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	sensorscx.h
api_name: 
-	*PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED
product:
- Windows
targetos: Windows
---

# *PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED callback function

## -description

Indicates that the history retrieval has completed. 

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXSENSORHISTORYRETRIEVALCOMPLETED *PfnSensorscxsensorhistoryretrievalcompleted; 

// Definition

VOID *PfnSensorscxsensorhistoryretrievalcompleted 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	SENSOROBJECT Sensor
	ULONG BytesWritten
	NTSTATUS InStatus
)
{...}

```

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param Sensor

A reference to a sensor object.

### -param BytesWritten

The number of bytes written to the sensor object's history.

### -param InStatus

The current status of the sensor object.

## -returns

Returns VOID.
