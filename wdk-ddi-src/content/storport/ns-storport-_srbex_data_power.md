---
UID: NS:storport._SRBEX_DATA_POWER
title: "_SRBEX_DATA_POWER"
author: windows-driver-content
description: The SRBEX_DATA_POWER structure contains the request data for an extended power SRB.
old-location: storage\srbex_data_power.htm
old-project: storage
ms.assetid: 61F5C316-5214-45A6-B4BA-DEE6A224E811
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSRBEX_DATA_POWER, PSRBEX_DATA_POWER, PSRBEX_DATA_POWER structure pointer [Storage Devices], SRBEX_DATA_POWER, SRBEX_DATA_POWER structure [Storage Devices], _SRBEX_DATA_POWER, storage.srbex_data_power, storport/PSRBEX_DATA_POWER, storport/SRBEX_DATA_POWER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	SRBEX_DATA_POWER
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA_POWER, *PSRBEX_DATA_POWER
req.product: Windows 10 or later.
---

# _SRBEX_DATA_POWER structure


## -description


The <b>SRBEX_DATA_POWER</b> structure contains the request data for an extended power SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypePower</b>.


### -field Length

Length of the data in this structure starting with the <b>SrbPowerFlags</b> member. Set to SRBEX_DATA_POWER_LENGTH.


### -field SrbPowerFlags

Indicates that the power request is for the adapter if SRB_POWER_FLAGS_ADAPTER_REQUEST is set and that storage device address is reserved. Otherwise, <i>SrbPowerFlags</i> will be <b>NULL</b>, indicating that the request is for the storage device specified by an address at <b>AddressOffset</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a> structure.


### -field Reserved

This member is reserved. Set to 0.


### -field DevicePowerState

An enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567578">STOR_DEVICE_POWER_STATE</a> that specifies the requested power state of the device. 


### -field PowerAction

An enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567587">STOR_POWER_ACTION</a> that specifies the type of system shutdown that is about to occur. This value is meaningful only if the device is moving into the D1, D2, or D3 power state as indicated by the <b>DevicePowerState</b> member.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567578">STOR_DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567587">STOR_POWER_ACTION</a>
 

 

