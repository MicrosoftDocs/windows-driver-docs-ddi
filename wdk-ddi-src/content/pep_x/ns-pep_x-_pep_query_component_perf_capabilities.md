---
UID: NS:pep_x._PEP_QUERY_COMPONENT_PERF_CAPABILITIES
title: "_PEP_QUERY_COMPONENT_PERF_CAPABILITIES"
author: windows-driver-content
description: The PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure specifies the number of performance state (P-state) sets that are defined for a component.
old-location: kernel\pep_query_component_perf_capabilities.htm
tech.root: kernel
ms.assetid: 6E1A4A3B-FA8B-4AAC-898F-CCFF77BFA962
ms.date: 4/30/2018
ms.keywords: "*PPEP_QUERY_COMPONENT_PERF_CAPABILITIES, PEP_QUERY_COMPONENT_PERF_CAPABILITIES, PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure [Kernel-Mode Driver Architecture], PPEP_QUERY_COMPONENT_PERF_CAPABILITIES, PPEP_QUERY_COMPONENT_PERF_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_COMPONENT_PERF_CAPABILITIES, kernel.pep_query_component_perf_capabilities, pepfx/PEP_QUERY_COMPONENT_PERF_CAPABILITIES, pepfx/PPEP_QUERY_COMPONENT_PERF_CAPABILITIES"
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
-	PEP_QUERY_COMPONENT_PERF_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: PEP_QUERY_COMPONENT_PERF_CAPABILITIES, *PPEP_QUERY_COMPONENT_PERF_CAPABILITIES
---

# _PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure


## -description


The <b>PEP_QUERY_COMPONENT_PERF_CAPABILITIES</b> structure specifies the number of performance state (P-state) sets that are defined for a component.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field SetCount

[out] The number of P-state sets that are defined for this component.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186839">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification. The <b>DeviceHandle</b> and <b>Component</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent. The <b>SetCount</b> member contains an output value that the PEP writes to the structure in response to the notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186839">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>
 

 

