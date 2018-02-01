---
UID: NS:poclass._BATTERY_INFORMATION
title: "_BATTERY_INFORMATION"
author: windows-driver-content
description: Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests.
old-location: battery\battery_information.htm
old-project: battery
ms.assetid: e9326d96-bd96-4493-a0b2-abe6b8f2401a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: BATTERY_INFORMATION, PBATTERY_INFORMATION structure pointer [Battery Devices], PBATTERY_INFORMATION, bat-struct_c2f83d6c-44f6-4e41-8f15-874edfc17b7c.xml, BATTERY_INFORMATION structure [Battery Devices], *PBATTERY_INFORMATION, poclass/PBATTERY_INFORMATION, poclass/BATTERY_INFORMATION, battery.battery_information, _BATTERY_INFORMATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poclass.h
apiname:
-	BATTERY_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PBATTERY_INFORMATION, BATTERY_INFORMATION"
---

# _BATTERY_INFORMATION structure


## -description


Battery miniclass drivers fill in this structure in response to certain <a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a> requests. 


## -syntax


````
typedef struct _BATTERY_INFORMATION {
  ULONG Capabilities;
  UCHAR Technology;
  UCHAR Reserved[3];
  UCHAR Chemistry[4];
  ULONG DesignedCapacity;
  ULONG FullChargedCapacity;
  ULONG DefaultAlert1;
  ULONG DefaultAlert2;
  ULONG CriticalBias;
  ULONG CycleCount;
} BATTERY_INFORMATION, *PBATTERY_INFORMATION;
````


## -struct-fields




### -field Capabilities

Specify battery capabilities as a ULONG value encoded with one or more of the following flags: 




#### BATTERY_CAPACITY_RELATIVE

Set this flag if the miniclass driver will report battery capacity and rate as a percentage of total capacity and rate rather than as absolute values. Otherwise, the miniclass driver should report capacity in milliwatt-hours and rate in milliwatts.


#### BATTERY_IS_SHORT_TERM

Set this flag if the battery is a UPS, intended for short-term, failsafe use. Clear the flag for any other type of device.


#### BATTERY_SET_CHARGE_SUPPORTED

Set this flag if the miniclass driver supports the <b>BatteryCharge </b>setting in calls to <i>BatteryMiniSetInformation</i>.


#### BATTERY_SET_DISCHARGE_SUPPORTED

Set this flag if the miniclass driver supports the <b>BatteryDischarge </b>setting in calls to <i>BatteryMiniSetInformation</i>.


#### BATTERY_SYSTEM_BATTERY

Set this flag if the battery can provide general power to run the system.


### -field Technology

Specify zero for a primary, nonrechargeable battery, or one for a secondary, rechargeable battery.


### -field Reserved

Reserved for system use.


### -field Chemistry

Specify a four-character string indicating the type of chemistry used in the battery. Possible values include "PbAc" (Lead Acid), "LION" (Lithium Ion), "NiCd" (Nickel Cadmium), "NiMH" (Nickel Metal Hydride), "NiZn" (Nickel Zinc), and "RAM" (Rechargeable Alkaline-Manganese). Additional values might be returned as additional battery types become available.


### -field DesignedCapacity

Specify the theoretical capacity of the battery when new, in milliwatt-hours. If BATTERY_CAPACITY_RELATIVE is set, the units are undefined.


### -field FullChargedCapacity

Specify the battery's current fully charged capacity, in milliwatt-hours. If BATTERY_CAPACITY_RELATIVE is set, the units are undefined. 


### -field DefaultAlert1

Specify the capacity (in milliwatt-hours) at which a low battery alert should occur. 


### -field DefaultAlert2

Specify the capacity (in milliwatt-hours) at which a warning battery alert should occur.


### -field CriticalBias

Specify the amount (in milliwatt-hours) of any small reserved charge that remains when the critical battery level shows zero. Miniclass drivers should subtract this value from the battery's <b>FullChargedCapacity</b> and remaining capacity (reported in <a href="..\poclass\ns-poclass-_battery_status.md">BATTERY_STATUS</a>) before reporting those values.


### -field CycleCount

Specify the number of charge/discharge cycles the battery has experienced, or zero if the battery does not support a cycle counter.


## -see-also

<a href="https://msdn.microsoft.com/04811f63-8a57-4b39-84c5-c9b7f803c057">BatteryMiniQueryStatus</a>

<a href="https://msdn.microsoft.com/bd96b79a-5670-4aaf-b72c-619818c2a2e7">BatteryMiniQueryInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20BATTERY_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

