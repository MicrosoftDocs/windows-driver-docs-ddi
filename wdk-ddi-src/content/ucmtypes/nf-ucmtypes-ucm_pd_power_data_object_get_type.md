---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_GET_TYPE
title: UCM_PD_POWER_DATA_OBJECT_GET_TYPE function (ucmtypes.h)
description: Retrieves the type of Power Data Object from the UCM_PD_POWER_DATA_OBJECT structure.
old-location: buses\ucm_pd_power_data_object_get_type.htm
tech.root: usbref
ms.assetid: ACB0AB92-5EC8-4792-AB40-853FC5AAD125
ms.date: 05/07/2018
keywords: ["UCM_PD_POWER_DATA_OBJECT_GET_TYPE function"]
ms.keywords: UCM_PD_POWER_DATA_OBJECT_GET_TYPE, UCM_PD_POWER_DATA_OBJECT_GET_TYPE function [Buses], buses.ucm_pd_power_data_object_get_type, ucmtypes/UCM_PD_POWER_DATA_OBJECT_GET_TYPE
f1_keywords:
 - "ucmtypes/UCM_PD_POWER_DATA_OBJECT_GET_TYPE"
 - "UCM_PD_POWER_DATA_OBJECT_GET_TYPE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ucmtypes.h
api_name:
- UCM_PD_POWER_DATA_OBJECT_GET_TYPE
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_PD_POWER_DATA_OBJECT_GET_TYPE function


## -description


Retrieves the type of Power Data Object from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structure. 


## -parameters




### -param Pdo [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structure that contains the type of Power Data Object.


## -returns



Returns the <b>Common.Type</b> member of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structure.




## -remarks



For information about the Power Data Object including the types of object, see Power Delivery specification. The Type member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> indicates the type of Power Data Object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a>
 

 

