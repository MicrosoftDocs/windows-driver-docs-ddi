---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function (ucmtypes.h)
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Battery Supply type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_battery.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function"]
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY, UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function [Buses], buses.ucm_pd_power_data_object_init_battery, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
 - ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtypes.h
api_name:
 - UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
---

# UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function


## -description

Initializes a <a href="/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structure as a Battery Supply type Power Data Object.

## -parameters

### -param Pdo 

[out]
A pointer to a <a href="/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>BatterySupplyPdo.Battery</b> member is set to <b>UcmPdPdoTypeBatterySupply</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a>
