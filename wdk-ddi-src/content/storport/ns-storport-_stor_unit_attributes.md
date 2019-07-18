---
UID: NS:storport._STOR_UNIT_ATTRIBUTES
title: _STOR_UNIT_ATTRIBUTES (storport.h)
description: The STOR_UNIT_ATTRIBUTES structure contains bitfields indicating attribute support for a storage device unit.
old-location: storage\stor_unit_attributes.htm
tech.root: storage
ms.assetid: 9677C044-354B-4575-B2EC-187D1B4E8C61
ms.date: 03/29/2018
ms.keywords: "*PSTOR_UNIT_ATTRIBUTES, PSTOR_UNIT_ATTRIBUTES, PSTOR_UNIT_ATTRIBUTES structure pointer [Storage Devices], STOR_UNIT_ATTRIBUTES, STOR_UNIT_ATTRIBUTES structure [Storage Devices], _STOR_UNIT_ATTRIBUTES, storage.stor_unit_attributes, storport/PSTOR_UNIT_ATTRIBUTES, storport/STOR_UNIT_ATTRIBUTES"
ms.topic: struct
f1_keywords:
 - "storport/STOR_UNIT_ATTRIBUTES"
req.header: storport.h
req.include-header: Storport.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Storport.h
api_name:
- STOR_UNIT_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: STOR_UNIT_ATTRIBUTES, *PSTOR_UNIT_ATTRIBUTES
---

# _STOR_UNIT_ATTRIBUTES structure


## -description


The <b>STOR_UNIT_ATTRIBUTES</b> structure contains bitfields indicating attribute support for a storage device unit.


## -struct-fields




### -field DeviceAttentionSupported

Set to 1 if device attention is supported for the unit. Otherwise, set to 0.


### -field AsyncNotificationSupported

Set to 1 if the device supports asynchronous notifications. Otherwise, set to 0.


### -field D3ColdNotSupported

Set to 1 if the D3 Cold power state is NOT supported. Otherwise, set to 0.


### -field Reserved

Reserved bits. Must be set to 0.


## -remarks



The unit attributes are registered with Storport  using this structure as a parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportsetunitattributes">StorPortSetUnitAttributes</a> routine.

If the miniport driver supports asynchronous notifications, the <b>AsyncNotificationSupported</b> field set to 1, it will send notifications to the Storport driver using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportasyncnotificationdetected">StorPortAsyncNotificationDetected</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportasyncnotificationdetected">StorPortAsyncNotificationDetected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportsetunitattributes">StorPortSetUnitAttributes</a>
 

 

