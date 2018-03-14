---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function
author: windows-driver-content
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Battery Supply type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_battery.htm
old-project: usbref
ms.assetid: DA191158-D920-4965-AC2B-7DDA8B541504
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY, UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function [Buses], buses.ucm_pd_power_data_object_init_battery, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	Ucmtypes.h
api_name:
-	UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---

# UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function


## -description


Initializes a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure as a Battery Supply type Power Data Object.


## -syntax


````
FORCEINLINE void UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY(
  _Out_ PUCM_PD_POWER_DATA_OBJECT Pdo
);
````


## -parameters




### -param Pdo [out]

A pointer to a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>BatterySupplyPdo.Battery</b> member is set to <b>UcmPdPdoTypeBatterySupply</b>.


## -returns



This function does not return a value.




## -see-also

<a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a>



 

 


