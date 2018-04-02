---
UID: NS:ntpoapi.BATTERY_REPORTING_SCALE
title: BATTERY_REPORTING_SCALE
author: windows-driver-content
description: Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests.
old-location: battery\battery_reporting_scale.htm
old-project: battery
ms.assetid: aea1d82d-39b8-4535-a5c3-fb987be1e43c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE structure [Battery Devices], PBATTERY_REPORTING_SCALE, PBATTERY_REPORTING_SCALE structure pointer [Battery Devices], bat-struct_6ecc4955-56b0-4c92-9ce2-46bcd7d6b273.xml, battery.battery_reporting_scale, ntpoapi/BATTERY_REPORTING_SCALE, ntpoapi/PBATTERY_REPORTING_SCALE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntpoapi.h
req.include-header: Batclass.h, Wdm.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntpoapi.h
api_name:
-	BATTERY_REPORTING_SCALE
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---

# BATTERY_REPORTING_SCALE structure


## -description


Battery miniclass drivers fill in this structure in response to certain <a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a> requests. 


## -struct-fields




### -field Granularity

Specify the granularity of the <b>Capacity</b> value, in milliwatt-hours. For most batteries, this value describes a monotonically increasing scale of capacity. For lithium-ion batteries, this value describes one of two possible scales: a gross measure of battery capacity, with a large granularity, or a finer measure as the capacity approaches zero.


### -field Capacity

Specify the battery capacity described by the corresponding granularity, in milliwatt-hours.


## -see-also




<a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a>
 

 

