---
UID: NS:poclass._BATTERY_MANUFACTURE_DATE
title: "_BATTERY_MANUFACTURE_DATE"
author: windows-driver-content
description: Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests.
old-location: battery\battery_manufacture_date.htm
old-project: battery
ms.assetid: 1ab9caa3-344a-49c8-8f40-75d9c251be04
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBATTERY_MANUFACTURE_DATE, BATTERY_MANUFACTURE_DATE, BATTERY_MANUFACTURE_DATE structure [Battery Devices], PBATTERY_MANUFACTURE_DATE, PBATTERY_MANUFACTURE_DATE structure pointer [Battery Devices], _BATTERY_MANUFACTURE_DATE, bat-struct_7c707930-4017-4761-94fc-e4322cd6ead9.xml, battery.battery_manufacture_date, poclass/BATTERY_MANUFACTURE_DATE, poclass/PBATTERY_MANUFACTURE_DATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: poclass.h
req.include-header: Batclass.h
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	poclass.h
api_name:
-	BATTERY_MANUFACTURE_DATE
product: Windows
targetos: Windows
req.typenames: BATTERY_MANUFACTURE_DATE, *PBATTERY_MANUFACTURE_DATE
---

# _BATTERY_MANUFACTURE_DATE structure


## -description


Battery miniclass drivers fill in this structure in response to certain <a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a> requests. 


## -syntax


````
typedef struct _BATTERY_MANUFACTURE_DATE {
  UCHAR  Day;
  UCHAR  Month;
  USHORT Year;
} BATTERY_MANUFACTURE_DATE, *PBATTERY_MANUFACTURE_DATE;
````


## -struct-fields




### -field Day

Specifies a value in the range 1 to 31, inclusive.


### -field Month

Specifies a value in the range 1 to 12, inclusive.


### -field Year

Specifies a value &gt;= 1996.


## -see-also

<a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20BATTERY_MANUFACTURE_DATE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

