---
UID: NS:storport._STORPORT_TELEMETRY_EVENT
title: "_STORPORT_TELEMETRY_EVENT"
author: windows-driver-content
description: The STORPORT_TELEMETRY_EVENT structure describes the miniport telemetry data payload.
old-location: storage\storport_telemetry_event.htm
old-project: storage
ms.assetid: 50A3EB6D-C485-4C04-8E88-9BD7D7ED0A62
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORPORT_TELEMETRY_EVENT, PSTORPORT_TELEMETRY_EVENT, PSTORPORT_TELEMETRY_EVENT structure pointer [Storage Devices], STORPORT_TELEMETRY_EVENT, STORPORT_TELEMETRY_EVENT structure [Storage Devices], _STORPORT_TELEMETRY_EVENT, storage.storport_telemetry_event, storport/PSTORPORT_TELEMETRY_EVENT, storport/STORPORT_TELEMETRY_EVENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	STORPORT_TELEMETRY_EVENT
product: Windows
targetos: Windows
req.typenames: STORPORT_TELEMETRY_EVENT, *PSTORPORT_TELEMETRY_EVENT
---

# _STORPORT_TELEMETRY_EVENT structure


## -description


The <b>STORPORT_TELEMETRY_EVENT</b> structure describes the miniport telemetry data payload.


## -struct-fields




### -field DriverVersion

Miniport driver version.


### -field EventId

A miniport defined identifier for the telemetry event.


### -field EventName

A miniport defined name for the telemetry event, which has the maximum length of <b>EVENT_NAME_MAX_LENGTH</b>.


### -field EventVersion

A miniport defined version for the telemetry event.


### -field Flags

Reserved.


### -field EventBufferLength

The length of <b>EventBuffer</b>, which should be not larger than <b>EVENT_BUFFER_MAX_LENGTH</b> that is 4KB.


### -field EventBuffer

A miniport defined telemetry payload, the length of which is <b>EventBufferLength</b>.


### -field ParameterName0

A description of the of the meaning of ParameterValue0. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue0

The value for parameter 0.


### -field ParameterName1

A description of the of the meaning of ParameterValue1. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue1

The value for parameter 1.


### -field ParameterName2

A description of the of the meaning of ParameterValue2. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue2

The value for parameter 2.


### -field ParameterName3

A description of the of the meaning of ParameterValue3. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue3

The value for parameter 3.


### -field ParameterName4

A description of the of the meaning of ParameterValue4. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue4

The value for parameter 4.


### -field ParameterName5

A description of the of the meaning of ParameterValue5. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue5

The value for parameter 5.


### -field ParameterName6

A description of the of the meaning of ParameterValue6. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue6

The value for parameter 6.


### -field ParameterName7

A description of the of the meaning of ParameterValue7. This parameter name string must be &lt;= EVENT_MAX_PARAM_NAME_LEN.


### -field ParameterValue7

The value for parameter 7.


## -remarks



A <b>STORPORT_TELEMETRY_EVENT</b> structure describes the miniport telemetry data payload. The miniport should fill it when calling StorPortLogTelemetry.




## -see-also




<a href="https://msdn.microsoft.com/3B32F31C-3850-43D4-9C6E-40D35B8AF4D4">StorPortLogTelemetry</a>
 

 

