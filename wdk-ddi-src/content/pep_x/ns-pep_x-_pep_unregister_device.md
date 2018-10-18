---
UID: NS:pep_x._PEP_UNREGISTER_DEVICE
title: "_PEP_UNREGISTER_DEVICE"
author: windows-driver-content
description: The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx).
old-location: kernel\pep_unregister_device.htm
tech.root: kernel
ms.assetid: B6A0F80C-8AE2-4FFE-A3EE-F0260A8774D6
ms.date: 04/30/2018
ms.keywords: "*PPEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_UNREGISTER_DEVICE, PPEP_UNREGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_UNREGISTER_DEVICE, kernel.pep_unregister_device, pepfx/PEP_UNREGISTER_DEVICE, pepfx/PPEP_UNREGISTER_DEVICE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_UNREGISTER_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PEP_UNREGISTER_DEVICE, *PPEP_UNREGISTER_DEVICE
---

# _PEP_UNREGISTER_DEVICE structure


## -description


The <b>PEP_UNREGISTER_DEVICE</b> structure identifies a device whose registration is being removed from the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_UNREGISTER_DEVICE</a>
 

 

