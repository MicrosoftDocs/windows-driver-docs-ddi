---
UID: NS:pepfx._PEP_QUERY_COMPONENT_PERF_CAPABILITIES
title: "_PEP_QUERY_COMPONENT_PERF_CAPABILITIES"
author: windows-driver-content
description: The PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure specifies the number of performance state (P-state) sets that are defined for a component.
old-location: kernel\pep_query_component_perf_capabilities.htm
old-project: kernel
ms.assetid: 6E1A4A3B-FA8B-4AAC-898F-CCFF77BFA962
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PPEP_QUERY_COMPONENT_PERF_CAPABILITIES, kernel.pep_query_component_perf_capabilities, PPEP_QUERY_COMPONENT_PERF_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], *PPEP_QUERY_COMPONENT_PERF_CAPABILITIES, PPEP_QUERY_COMPONENT_PERF_CAPABILITIES, PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure [Kernel-Mode Driver Architecture], _PEP_QUERY_COMPONENT_PERF_CAPABILITIES, pepfx/PEP_QUERY_COMPONENT_PERF_CAPABILITIES, PEP_QUERY_COMPONENT_PERF_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
-	PEP_QUERY_COMPONENT_PERF_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PPEP_QUERY_COMPONENT_PERF_CAPABILITIES, PEP_QUERY_COMPONENT_PERF_CAPABILITIES"
---

# _PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure


## -description


The <b>PEP_QUERY_COMPONENT_PERF_CAPABILITIES</b> structure specifies the number of performance state (P-state) sets that are defined for a component.


## -syntax


````
typedef struct _PEP_QUERY_COMPONENT_PERF_CAPABILITIES {
  PEPHANDLE DeviceHandle;
  ULONG     Component;
  ULONG     SetCount;
} PEP_QUERY_COMPONENT_PERF_CAPABILITIES, *PPEP_QUERY_COMPONENT_PERF_CAPABILITIES;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field SetCount

[out] The number of P-state sets that are defined for this component.


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186839">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification. The <b>DeviceHandle</b> and <b>Component</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent. The <b>SetCount</b> member contains an output value that the PEP writes to the structure in response to the notification.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186839">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a>

<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

