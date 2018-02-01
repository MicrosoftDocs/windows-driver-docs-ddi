---
UID: NS:ntddk._BDCB_STATUS_UPDATE_CONTEXT
title: "_BDCB_STATUS_UPDATE_CONTEXT"
author: windows-driver-content
description: The BDCB_STATUS_UPDATE_CONTEXT structure describes a status update provided by Windows to a boot-start driver's BOOT_DRIVER_CALLBACK_FUNCTION routine.
old-location: kernel\bdcb_status_update_context.htm
old-project: kernel
ms.assetid: 5DB29B81-2D7A-44FA-B5A9-FEF87C6A926D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: BDCB_STATUS_UPDATE_CONTEXT, ntddk/PBDCB_STATUS_UPDATE_CONTEXT, BDCB_STATUS_UPDATE_CONTEXT structure [Kernel-Mode Driver Architecture], *PBDCB_STATUS_UPDATE_CONTEXT, ntddk/BDCB_STATUS_UPDATE_CONTEXT, _BDCB_STATUS_UPDATE_CONTEXT, PBDCB_STATUS_UPDATE_CONTEXT structure pointer [Kernel-Mode Driver Architecture], kernel.bdcb_status_update_context, PBDCB_STATUS_UPDATE_CONTEXT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	BDCB_STATUS_UPDATE_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PBDCB_STATUS_UPDATE_CONTEXT, BDCB_STATUS_UPDATE_CONTEXT"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BDCB_STATUS_UPDATE_CONTEXT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

