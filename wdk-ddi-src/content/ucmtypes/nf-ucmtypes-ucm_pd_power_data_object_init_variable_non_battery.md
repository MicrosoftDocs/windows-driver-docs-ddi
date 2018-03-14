---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function
author: windows-driver-content
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Variable Supply Non Battery type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_variable_non_battery.htm
old-project: usbref
ms.assetid: BBC8975A-E5B1-4137-83D8-891075A8F4D0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY, UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function [Buses], buses.ucm_pd_power_data_object_init_variable_non_battery, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
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
-	UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---

# UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function


## -description


Initializes a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure as a Variable Supply Non Battery type Power Data Object.


## -syntax


````
FORCEINLINE void UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY(
  _Out_ PUCM_PD_POWER_DATA_OBJECT Pdo
);
````


## -parameters




### -param Pdo [out]

A pointer to a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>VariableSupplyNonBatteryPdo.VariableSupportNonBattery</b> member is set to <b>UcmPdPdoTypeVariableSupplyNonBattery</b>.


## -returns



This function does not return a value.




## -see-also

<a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a>



 

 


