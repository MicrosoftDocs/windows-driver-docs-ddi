---
UID: NS:pep_x._PEP_WORK_IDLE_STATE
title: "_PEP_WORK_IDLE_STATE"
author: windows-driver-content
description: The PEP_WORK_IDLE_STATE structure contains a request to transition a component to an Fx power state.
old-location: kernel\pep_work_idle_state.htm
tech.root: kernel
ms.assetid: DD8C454D-D0F6-456B-B59A-2E4DF2D757B5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_WORK_IDLE_STATE, PEP_WORK_IDLE_STATE, PEP_WORK_IDLE_STATE structure [Kernel-Mode Driver Architecture], PPEP_WORK_IDLE_STATE, PPEP_WORK_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_IDLE_STATE, kernel.pep_work_idle_state, pep_x/PEP_WORK_IDLE_STATE, pep_x/PPEP_WORK_IDLE_STATE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pep_x.h
api_name:
-	PEP_WORK_IDLE_STATE
product:
- Windows
targetos: Windows
req.typenames: PEP_WORK_IDLE_STATE, *PPEP_WORK_IDLE_STATE
---

# _PEP_WORK_IDLE_STATE structure


## -description


The <b>PEP_WORK_IDLE_STATE</b> structure contains a request to transition a component to an F<i>x</i> power state.


## -struct-fields




### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field State

The target F<i>x</i> power state to transition the component to. If this parameter is 0, the target state is F0; if this parameter is 1, the target state is F1; and so on. For more information about F<i>x</i> power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450935">Component-Level Power Management</a>.


## -remarks



The <b>IdleState</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_IDLE_STATE</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a>
 

 

