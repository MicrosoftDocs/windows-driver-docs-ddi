---
UID: NS:ntddk._BDCB_STATUS_UPDATE_CONTEXT
title: "_BDCB_STATUS_UPDATE_CONTEXT"
author: windows-driver-content
description: The BDCB_STATUS_UPDATE_CONTEXT structure describes a status update provided by Windows to a boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\bdcb_status_update_context.htm
old-project: kernel
ms.assetid: 5DB29B81-2D7A-44FA-B5A9-FEF87C6A926D
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PBDCB_STATUS_UPDATE_CONTEXT, BDCB_STATUS_UPDATE_CONTEXT, BDCB_STATUS_UPDATE_CONTEXT structure [Kernel-Mode Driver Architecture], PBDCB_STATUS_UPDATE_CONTEXT, PBDCB_STATUS_UPDATE_CONTEXT structure pointer [Kernel-Mode Driver Architecture], _BDCB_STATUS_UPDATE_CONTEXT, kernel.bdcb_status_update_context, ntddk/BDCB_STATUS_UPDATE_CONTEXT, ntddk/PBDCB_STATUS_UPDATE_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	BDCB_STATUS_UPDATE_CONTEXT
product: Windows
targetos: Windows
req.typenames: BDCB_STATUS_UPDATE_CONTEXT, *PBDCB_STATUS_UPDATE_CONTEXT
---

# _BDCB_STATUS_UPDATE_CONTEXT structure


## -description


The BDCB_STATUS_UPDATE_CONTEXT structure describes a status update provided by Windows to a boot-start driver's <a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a> routine.


## -syntax


````
typedef struct _BDCB_STATUS_UPDATE_CONTEXT {
  BDCB_STATUS_UPDATE_TYPE StatusType;
} BDCB_STATUS_UPDATE_CONTEXT, *PBDCB_STATUS_UPDATE_CONTEXT;
````


## -struct-fields




### -field StatusType

The type of the status update.


## -remarks



Boot-start drivers must not unregister their boot-start driver callbacks during a callback. Doing so may result in a bug check. To properly unregister a boot-driver callback, boot-start drivers must specify an <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine in their <a href="..\wdm\ns-wdm-_driver_object.md">driver object</a> and call <a href="..\ntddk\nf-ntddk-iounregisterbootdrivercallback.md">IoUnRegisterBootDriverCallback</a> from within the Unload dispatch routine.




## -see-also

<a href="..\ntddk\nf-ntddk-iounregisterbootdrivercallback.md">IoUnRegisterBootDriverCallback</a>



<a href="..\ntddk\nf-ntddk-ioregisterbootdrivercallback.md">BOOT_DRIVER_CALLBACK_FUNCTION</a>



<a href="..\ntddk\ne-ntddk-_bdcb_status_update_type.md">BDCB_STATUS_UPDATE_TYPE</a>



 

 


