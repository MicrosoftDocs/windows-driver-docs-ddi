---
UID: NS:sensorscx._SENSOR_CONTROLLER_CONFIG
title: "_SENSOR_CONTROLLER_CONFIG"
description: This structure contains pointers to callback functions that must be implemented by the driver, and passed on to the class extension to call.
old-location: sensors\sensor_controller_config.htm
tech.root: sensors
ms.assetid: EEAC4D16-D0B8-4147-AD2D-7EE60853EBDD
ms.date: 05/03/2018
ms.keywords: "*PSENSOR_CONTROLLER_CONFIG, PSENSOR_CONTROLLER_CONFIG, PSENSOR_CONTROLLER_CONFIG structure pointer [Sensor Devices], SENSOR_CONTROLLER_CONFIG, SENSOR_CONTROLLER_CONFIG structure [Sensor Devices], _SENSOR_CONTROLLER_CONFIG, sensors.sensor_controller_config, sensorscx/PSENSOR_CONTROLLER_CONFIG, sensorscx/SENSOR_CONTROLLER_CONFIG"
ms.topic: struct
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	SensorsCx.h
api_name:
-	SENSOR_CONTROLLER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: SENSOR_CONTROLLER_CONFIG, *PSENSOR_CONTROLLER_CONFIG
---

# _SENSOR_CONTROLLER_CONFIG structure


## -description


This structure contains pointers to callback functions that must be implemented by the driver, and passed on to the class extension to call.


## -struct-fields




### -field Size

The allocated size of this structure (in bytes).


### -field DriverIsPowerPolicyOwner

Indicates whether or not driver owns the power policy. This value must be either WdfFalse, WdfUseDefault, or WdfTrue. For partners to take advantage of pep-based power management, they must set this flag to WdfFalse or WdfUseDefault and remove any _PSx method in their ACPI tables.


### -field EvtSensorStart

This callback function starts the sensor based on the default properties specified by the driver, or properties set by the class extension.


### -field EvtSensorStop

This callback function stops the sensor.


### -field EvtSensorGetSupportedDataFields

This callback function returns a list of data fields supported by the specified sensor.


### -field EvtSensorGetDataFieldProperties

This callback function returns the properties of a given data field associated with a sensor.


### -field EvtSensorGetDataInterval

This callback function returns the data interval for a specified sensor.


### -field EvtSensorSetDataInterval

This callback function sets the data interval for a specified sensor.


### -field EvtSensorGetDataThresholds

This callback function returns the thresholds that are associated with a sensor.


### -field EvtSensorSetDataThresholds

This callback function stops the sensor.


### -field EvtSensorGetProperties

This callback function returns the properties for a given sensor.


### -field EvtSensorDeviceIoControl

This callback function handles IOCTLs outside of the class extension.<div class="alert"><b>Note</b>  If the driver needs to queue the IRP, it must copy the IRP to an IoQueue that the driver owns. This will prevent all IRPs for the driver to be stalled until completion.</div>
<div> </div>



### -field EvtSensorStartHistory

 


### -field EvtSensorStopHistory

 


### -field EvtSensorClearHistory

 


### -field EvtSensorStartHistoryRetrieval

 


### -field EvtSensorCancelHistoryRetrieval

 


### -field EvtSensorSetBatchLatency

This callback function sets the batch latency for a specified sensor.


### -field EvtSensorStartStateChangeNotification

 


### -field EvtSensorStopStateChangeNotification

 


### -field EvtSensorEnableWake

 


### -field EvtSensorDisableWake

 




## -remarks



This structure is given to the class extension using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957086">SensorsCxDeviceInitialize</a> function. If any of the following function pointers are not set, the driver will fail to load:

<ul>
<li>EvtSensorStart</li>
<li>EvtSensorStop</li>
<li>EvtSensorGetSupportedDataFields</li>
<li>EvtSensorGetDataFieldProperties</li>
<li>EvtSensorGetDataInterval</li>
<li>EvtSensorSetDataInterval</li>
<li>EvtSensorGetDataThresholds</li>
<li>EvtSensorSetDataThresholds</li>
<li>EvtSensorGetProperties</li>
</ul>
Each function returns STATUS_SUCCESS when completed successfully.

<div class="alert"><b>Note</b>  The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.

</div>
<div> </div>




