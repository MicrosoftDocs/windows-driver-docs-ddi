---
UID: NS:pep_x._PEP_WORK_DEVICE_POWER
title: "_PEP_WORK_DEVICE_POWER"
author: windows-driver-content
description: The PEP_WORK_DEVICE_POWER structure describes the new power requirements for the specified device.
old-location: kernel\pep_work_device_power.htm
old-project: kernel
ms.assetid: 5B39DFE1-3830-4650-9BB9-A03A040F1015
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_WORK_DEVICE_POWER, PEP_WORK_DEVICE_POWER, PEP_WORK_DEVICE_POWER structure [Kernel-Mode Driver Architecture], PPEP_WORK_DEVICE_POWER, PPEP_WORK_DEVICE_POWER structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_DEVICE_POWER, kernel.pep_work_device_power, pep_x/PEP_WORK_DEVICE_POWER, pep_x/PPEP_WORK_DEVICE_POWER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pep_x.h
api_name:
-	PEP_WORK_DEVICE_POWER
product: Windows
targetos: Windows
req.typenames: PEP_WORK_DEVICE_POWER, *PPEP_WORK_DEVICE_POWER
---

# _PEP_WORK_DEVICE_POWER structure


## -description


The <b>PEP_WORK_DEVICE_POWER</b> structure describes the new power requirements for the specified device.


## -syntax


````
typedef struct _PEP_WORK_DEVICE_POWER {
  POHANDLE DeviceHandle;
  BOOLEAN  PowerRequired;
} PEP_WORK_DEVICE_POWER, *PPEP_WORK_DEVICE_POWER;
````


## -struct-fields




### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


### -field PowerRequired

Whether the device requires power. Set to TRUE if the device requires power and the device driver <u>must</u> bring the device back to the D0 power state. Set to FALSE if the device is not required to stay turned on and the driver is permitted to transition the device from D0 to a low-power state.


## -remarks



The <b>DevicePower</b> member of the <a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_DEVICE_POWER</b> structure.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="..\pepfx\ns-pepfx-_pep_work_information.md">PEP_WORK_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_WORK_DEVICE_POWER structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

