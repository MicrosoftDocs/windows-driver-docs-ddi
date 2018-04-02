---
UID: NC:wdm.PREENUMERATE_SELF
title: PREENUMERATE_SELF
author: windows-driver-content
description: A ReenumerateSelf routine requests that a bus driver reenumerate a child device.
old-location: kernel\reenumerateself.htm
old-project: kernel
ms.assetid: ee669f35-87a5-4c5e-9936-b9135a1459e1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PREENUMERATE_SELF, ReenumerateSelf, ReenumerateSelf routine [Kernel-Mode Driver Architecture], drvr_interface_208efec1-4236-441b-a4b8-45a9539e4d84.xml, kernel.reenumerateself, wdm/ReenumerateSelf
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista.
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
-	UserDefined
api_location:
-	wdm.h
api_name:
-	ReenumerateSelf
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PREENUMERATE_SELF callback


## -description


A <i>ReenumerateSelf</i> routine requests that a bus driver reenumerate a child device.


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560839">REENUMERATE_SELF_INTERFACE_STANDARD</a> structure.


## -returns



None




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560839">REENUMERATE_SELF_INTERFACE_STANDARD</a> interface structure supplies a pointer to the <i>ReenumerateSelf</i> routine.

If the bus driver can process the request at the time of the routine call, the bus driver asynchronously reports the device as missing in a subsequent <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> BusRelations query. This report causes the current device instance to receive <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> requests. After the surprise removal has been processed, a new instance of the device is enumerated and the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine is called to rebuild the device stack.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560839">REENUMERATE_SELF_INTERFACE_STANDARD</a>
 

 

