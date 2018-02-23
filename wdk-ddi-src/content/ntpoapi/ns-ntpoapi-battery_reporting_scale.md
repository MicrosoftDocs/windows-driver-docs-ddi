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
ms.keywords: BATTERY_REPORTING_SCALE, PBATTERY_REPORTING_SCALE, bat-struct_6ecc4955-56b0-4c92-9ce2-46bcd7d6b273.xml, ntpoapi/BATTERY_REPORTING_SCALE, battery.battery_reporting_scale, PBATTERY_REPORTING_SCALE structure pointer [Battery Devices], ntpoapi/PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE structure [Battery Devices], *PBATTERY_REPORTING_SCALE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntpoapi.h
apiname:
-	BATTERY_REPORTING_SCALE
product: Windows
targetos: Windows
req.typenames: "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE"
---

# BATTERY_REPORTING_SCALE structure


## -description


Battery miniclass drivers fill in this structure in response to certain <a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a> requests. 


## -syntax


````
typedef struct {
  ULONG Granularity;
  ULONG Capacity;
} BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE;
````


## -struct-fields




### -field Granularity

Specify the granularity of the <b>Capacity</b> value, in milliwatt-hours. For most batteries, this value describes a monotonically increasing scale of capacity. For lithium-ion batteries, this value describes one of two possible scales: a gross measure of battery capacity, with a large granularity, or a finer measure as the capacity approaches zero.


### -field Capacity

Specify the battery capacity described by the corresponding granularity, in milliwatt-hours.


## -see-also

<a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20BATTERY_REPORTING_SCALE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

