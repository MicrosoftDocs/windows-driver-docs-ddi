---
UID: NS:pep_x._PEP_DEVICE_PLATFORM_CONSTRAINTS
title: "_PEP_DEVICE_PLATFORM_CONSTRAINTS"
description: The PEP_DEVICE_PLATFORM_CONSTRAINTS structure specifies the constraints for entry to the various Dx power states that are supported by a device.
old-location: kernel\pep_device_platform_constraints.htm
tech.root: kernel
ms.assetid: C9CC652F-16D4-4F88-BE8F-6CC7008F65DB
ms.date: 04/30/2018
ms.keywords: "*PPEP_DEVICE_PLATFORM_CONSTRAINTS, PEP_DEVICE_PLATFORM_CONSTRAINTS, PEP_DEVICE_PLATFORM_CONSTRAINTS structure [Kernel-Mode Driver Architecture], PPEP_DEVICE_PLATFORM_CONSTRAINTS, PPEP_DEVICE_PLATFORM_CONSTRAINTS structure pointer [Kernel-Mode Driver Architecture], _PEP_DEVICE_PLATFORM_CONSTRAINTS, kernel.pep_device_platform_constraints, pepfx/PEP_DEVICE_PLATFORM_CONSTRAINTS, pepfx/PPEP_DEVICE_PLATFORM_CONSTRAINTS"
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
-	PEP_DEVICE_PLATFORM_CONSTRAINTS
product:
- Windows
targetos: Windows
req.typenames: PEP_DEVICE_PLATFORM_CONSTRAINTS, *PPEP_DEVICE_PLATFORM_CONSTRAINTS
---

# _PEP_DEVICE_PLATFORM_CONSTRAINTS structure


## -description


The <b>PEP_DEVICE_PLATFORM_CONSTRAINTS</b> structure specifies the constraints for entry to the various D<i>x</i> power states that are supported by a device.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field MinimumDStates

[in] A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a> enumeration values that indicate the lowest-powered D<i>x</i> (device power) state the device can enter for each platform idle state.


### -field PlatformStateCount

[in] The number of elements in the array pointed to by the <b>MinimumDStates</b> member. This member contains the platform state count that the PEP supplied in response to a previous <a href="https://msdn.microsoft.com/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186704">PEP_DPM_DEVICE_IDLE_CONSTRAINTS</a> notification. All three members of this structure contain input values that are supplied by the Windows power management framework (PoFx). In response to this notification, the PEP writes <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a> enumeration values to the elements of the array pointed to by the <b>MinimumDStates</b> member. PoFx allocates the storage for this array before sending the notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186704">PEP_DPM_DEVICE_IDLE_CONSTRAINTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>
 

 

