---
UID: NS:pep_x._PEP_ABANDON_DEVICE
title: "_PEP_ABANDON_DEVICE" (pep_x.h)
description: The PEP_ABANDON_DEVICE structure identifies a device that has been abandoned and will no longer be used by the operating system.
old-location: kernel\pep_abandon_device.htm
tech.root: kernel
ms.assetid: 15F54054-F20B-43A6-8BCD-3A1C47433B12
ms.date: 04/30/2018
ms.keywords: "*PPEP_ABANDON_DEVICE, PEP_ABANDON_DEVICE, PEP_ABANDON_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ABANDON_DEVICE, PPEP_ABANDON_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ABANDON_DEVICE, kernel.pep_abandon_device, pepfx/PEP_ABANDON_DEVICE, pepfx/PPEP_ABANDON_DEVICE"
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
-	PEP_ABANDON_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PEP_ABANDON_DEVICE, *PPEP_ABANDON_DEVICE
---

# _PEP_ABANDON_DEVICE structure


## -description


The <b>PEP_ABANDON_DEVICE</b> structure identifies a device that has been abandoned and will no longer be used by the operating system.


## -struct-fields




### -field DeviceId

[in] A string that uniquely identifies the device. This member is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/install/device-identification-strings">device identification string</a>.


### -field DeviceAccepted

[out] Whether the PEP claims ownership of the device. The PEP sets this member to TRUE to claim ownership of the device, or to FALSE to indicate that it does not own the device.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186656">PEP_DPM_ABANDON_DEVICE</a> notification. The <b>DeviceId</b> member of the structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). The <b>DeviceAccepted</b> member contains an output value that the PEP writes to the structure in response to this notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186656">PEP_DPM_ABANDON_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

