---
UID: NE:ntddk._BDCB_STATUS_UPDATE_TYPE
title: "_BDCB_STATUS_UPDATE_TYPE"
author: windows-driver-content
description: The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates.
old-location: kernel\bdcb_status_update_type.htm
tech.root: kernel
ms.assetid: E18AD58C-74D0-4CA7-9EE5-F96863F88E26
ms.date: 4/30/2018
ms.keywords: "*PBDCB_STATUS_UPDATE_TYPE, BDCB_STATUS_UPDATE_TYPE, BDCB_STATUS_UPDATE_TYPE enumeration [Kernel-Mode Driver Architecture], BdCbStatusPrepareForDependecyLoad, BdCbStatusPrepareForDriverLoad, BdCbStatusPrepareForUnload, _BDCB_STATUS_UPDATE_TYPE, kernel.bdcb_status_update_type, ntddk/BDCB_STATUS_UPDATE_TYPE, ntddk/BdCbStatusPrepareForDependecyLoad, ntddk/BdCbStatusPrepareForDriverLoad, ntddk/BdCbStatusPrepareForUnload"
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
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
-	ntddk.h
api_name:
-	BDCB_STATUS_UPDATE_TYPE
product:
- Windows
targetos: Windows
req.typenames: BDCB_STATUS_UPDATE_TYPE, *PBDCB_STATUS_UPDATE_TYPE
---

# _BDCB_STATUS_UPDATE_TYPE enumeration


## -description


The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates.


## -enum-fields




### -field BdCbStatusPrepareForDependencyLoad


### -field BdCbStatusPrepareForDriverLoad

Windows has completed loading driver dependencies and will start loading boot-start drivers.


### -field BdCbStatusPrepareForUnload

Windows has completed the initialization of all boot-start drivers. After the completion of this callback, the Boot Driver Callback Facility will be torn down and no more callbacks will be received. During this callback, Early Launch AM drivers must clean up and prepare to be unloaded.


#### - BdCbStatusPrepareForDependecyLoad

Windows will start loading driver dependencies next.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406363">BDCB_STATUS_UPDATE_CONTEXT</a>



<a href="https://msdn.microsoft.com/28BA4B54-F493-4D79-89DF-D890EBCF1E9C">BOOT_DRIVER_CALLBACK_FUNCTION</a>
 

 

