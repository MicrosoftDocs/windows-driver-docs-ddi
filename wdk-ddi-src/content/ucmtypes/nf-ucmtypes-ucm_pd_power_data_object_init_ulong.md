---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_ULONG
title: UCM_PD_POWER_DATA_OBJECT_INIT_ULONG function (ucmtypes.h)
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure by interpreting Power Data Object values and sets each field correctly.
old-location: buses\ucm_pd_power_data_object_init_ulong.htm
tech.root: usbref
ms.assetid: F5520F9F-159E-42D9-A7F4-426CB935D29D
ms.date: 05/07/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_ULONG, UCM_PD_POWER_DATA_OBJECT_INIT_ULONG function [Buses], buses.ucm_pd_power_data_object_init_ulong, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_ULONG
ms.topic: function
f1_keywords:
 - "ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_ULONG"
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
- UCM_PD_POWER_DATA_OBJECT_INIT_ULONG
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_PD_POWER_DATA_OBJECT_INIT_ULONG function


## -description


Initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a>  structure by interpreting Power Data Object values and sets each field correctly.



## -parameters




### -param Pdo [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structure.


### -param UlongInLittleEndian [in]

The ULONG value to set in the <b>Ul</b> member of   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a>.


## -remarks



A Power Data Object, as defined by the Power Delivery specification,  is a 32-bit value. The hardware is expected to retrieve the Power Data Objects as 32-bit values. This utility function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a>  structure by interpreting those values and setting each field correctly.


The 4 byte value is expected to be in little-endian format.
The  structure is 4 bytes and the client driver can memcopy the Power Data Objects from the hardware into an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a> structures.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ns-ucmtypes-_ucm_pd_power_data_object">UCM_PD_POWER_DATA_OBJECT</a>
 

 

