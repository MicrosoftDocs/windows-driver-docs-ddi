---
UID: NS:pep_x._PEP_UNREGISTER_DEVICE
title: "_PEP_UNREGISTER_DEVICE"
author: windows-driver-content
description: The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx).
old-location: kernel\pep_unregister_device.htm
old-project: kernel
ms.assetid: B6A0F80C-8AE2-4FFE-A3EE-F0260A8774D6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: pepfx/PEP_UNREGISTER_DEVICE, PPEP_UNREGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_UNREGISTER_DEVICE, kernel.pep_unregister_device, *PPEP_UNREGISTER_DEVICE, pepfx/PPEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pepfx.h
apiname:
-	PEP_UNREGISTER_DEVICE
product: Windows
targetos: Windows
req.typenames: "*PPEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE"
---

# _PEP_UNREGISTER_DEVICE structure


## -description


The <b>PEP_UNREGISTER_DEVICE</b> structure identifies a device whose registration is being removed from the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).


## -syntax


````
typedef struct _PEP_UNREGISTER_DEVICE {
  PEPHANDLE DeviceHandle;
} PEP_UNREGISTER_DEVICE, *PPEP_UNREGISTER_DEVICE;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). 




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_UNREGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_UNREGISTER_DEVICE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

