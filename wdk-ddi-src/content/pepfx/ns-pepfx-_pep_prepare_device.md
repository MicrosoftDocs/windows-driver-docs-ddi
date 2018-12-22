---
UID: NS:pepfx._PEP_PREPARE_DEVICE
title: "_PEP_PREPARE_DEVICE"
description: The PEP_PREPARE_DEVICE structure identifies a device that must be started up in preparation for its use by the operating system.
old-location: kernel\pep_prepare_device.htm
tech.root: kernel
ms.assetid: 1D47C803-693B-4205-9D25-82489BFEC82C
ms.date: 04/30/2018
ms.keywords: "*PPEP_PREPARE_DEVICE, PEP_PREPARE_DEVICE, PEP_PREPARE_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_PREPARE_DEVICE, PPEP_PREPARE_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_PREPARE_DEVICE, kernel.pep_prepare_device, pepfx/PEP_PREPARE_DEVICE, pepfx/PPEP_PREPARE_DEVICE"
ms.topic: struct
req.header: pepfx.h
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
-	PEP_PREPARE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PEP_PREPARE_DEVICE, *PPEP_PREPARE_DEVICE
---

# _PEP_PREPARE_DEVICE structure


## -description


The <b>PEP_PREPARE_DEVICE</b> structure identifies a device that must be started up in preparation for its use by the operating system.


## -struct-fields




### -field DeviceId

[in] A string that uniquely identifies the device. This member is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/install/device-identification-strings">device identification string</a>.


### -field DeviceAccepted

[out] Whether the PEP claims ownership of the device. The PEP sets this member to TRUE to claim ownership of the device, or to FALSE to indicate that it does not own the device. The PEP that claims ownership is responsible for handling <a href="https://msdn.microsoft.com/library/windows/hardware/mt186631">device power management (DPM) notifications</a> for the device.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186832">PEP_DPM_PREPARE_DEVICE</a> notification. The <b>DeviceId</b> member of the structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). The <b>DeviceAccepted</b> member contains an output value that the PEP writes to the structure in response to this notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186832">PEP_DPM_PREPARE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

