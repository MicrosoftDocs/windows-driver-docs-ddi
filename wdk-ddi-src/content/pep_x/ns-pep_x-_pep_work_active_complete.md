---
UID: NS:pep_x._PEP_WORK_ACTIVE_COMPLETE
title: "_PEP_WORK_ACTIVE_COMPLETE"
author: windows-driver-content
description: The PEP_WORK_ACTIVE_COMPLETE structure identifies a component that is now in the active condition.
old-location: kernel\pep_work_active_complete.htm
tech.root: kernel
ms.assetid: DD7D7E5F-D35C-40B4-B414-A6D2EB8D3A02
ms.date: 04/30/2018
ms.keywords: "*PPEP_WORK_ACTIVE_COMPLETE, PEP_WORK_ACTIVE_COMPLETE, PEP_WORK_ACTIVE_COMPLETE structure [Kernel-Mode Driver Architecture], PPEP_WORK_ACTIVE_COMPLETE, PPEP_WORK_ACTIVE_COMPLETE structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_ACTIVE_COMPLETE, kernel.pep_work_active_complete, pep_x/PEP_WORK_ACTIVE_COMPLETE, pep_x/PPEP_WORK_ACTIVE_COMPLETE"
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
-	PEP_WORK_ACTIVE_COMPLETE
product:
- Windows
targetos: Windows
req.typenames: PEP_WORK_ACTIVE_COMPLETE, *PPEP_WORK_ACTIVE_COMPLETE
---

# _PEP_WORK_ACTIVE_COMPLETE structure


## -description


The <b>PEP_WORK_ACTIVE_COMPLETE</b> structure identifies a component that is now in the <i>active</i> condition.


## -struct-fields




### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -remarks



The <b>ActiveComplete</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_ACTIVE_COMPLETE</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a>
 

 

