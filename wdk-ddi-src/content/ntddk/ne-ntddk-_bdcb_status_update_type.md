---
UID: NE:ntddk._BDCB_STATUS_UPDATE_TYPE
title: _BDCB_STATUS_UPDATE_TYPE (ntddk.h)
description: The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates.
old-location: kernel\bdcb_status_update_type.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["BDCB_STATUS_UPDATE_TYPE enumeration"]
ms.keywords: "*PBDCB_STATUS_UPDATE_TYPE, BDCB_STATUS_UPDATE_TYPE, BDCB_STATUS_UPDATE_TYPE enumeration [Kernel-Mode Driver Architecture], BdCbStatusPrepareForDependecyLoad, BdCbStatusPrepareForDriverLoad, BdCbStatusPrepareForUnload, _BDCB_STATUS_UPDATE_TYPE, kernel.bdcb_status_update_type, ntddk/BDCB_STATUS_UPDATE_TYPE, ntddk/BdCbStatusPrepareForDependecyLoad, ntddk/BdCbStatusPrepareForDriverLoad, ntddk/BdCbStatusPrepareForUnload"
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
targetos: Windows
req.typenames: BDCB_STATUS_UPDATE_TYPE, *PBDCB_STATUS_UPDATE_TYPE
f1_keywords:
 - _BDCB_STATUS_UPDATE_TYPE
 - ntddk/_BDCB_STATUS_UPDATE_TYPE
 - PBDCB_STATUS_UPDATE_TYPE
 - ntddk/PBDCB_STATUS_UPDATE_TYPE
 - BDCB_STATUS_UPDATE_TYPE
 - ntddk/BDCB_STATUS_UPDATE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _BDCB_STATUS_UPDATE_TYPE
 - PBDCB_STATUS_UPDATE_TYPE
 - BDCB_STATUS_UPDATE_TYPE
---

# _BDCB_STATUS_UPDATE_TYPE enumeration


## -description

The BDCB_STATUS_UPDATE_TYPE enumeration lists the types of boot-driver callback status updates.

## -enum-fields

### -field BdCbStatusPrepareForDependencyLoad

Windows will start loading driver dependencies next.

### -field BdCbStatusPrepareForDriverLoad

Windows has completed loading driver dependencies and will start loading boot-start drivers.

### -field BdCbStatusPrepareForUnload

Windows has completed the initialization of all boot-start drivers. After the completion of this callback, the Boot Driver Callback Facility will be torn down and no more callbacks will be received. During this callback, Early Launch AM drivers must clean up and prepare to be unloaded.


#### - BdCbStatusPrepareForDependecyLoad

Windows will start loading driver dependencies next.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_bdcb_status_update_context">BDCB_STATUS_UPDATE_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterbootdrivercallback">BOOT_DRIVER_CALLBACK_FUNCTION</a>

