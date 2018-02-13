---
UID: NS:pepfx._PEP_REGISTER_COMPONENT_PERF_STATES
title: "_PEP_REGISTER_COMPONENT_PERF_STATES"
author: windows-driver-content
description: The PEP_REGISTER_COMPONENT_PERF_STATES structure describes the performance states (P-states) of the specified component.
old-location: kernel\pep_register_component_perf_states.htm
old-project: kernel
ms.assetid: 063ADC0A-3455-4966-A11C-BDD5BA08A685
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PEP_REGISTER_COMPONENT_PERF_STATES, pepfx/PPEP_REGISTER_COMPONENT_PERF_STATES, PPEP_REGISTER_COMPONENT_PERF_STATES structure pointer [Kernel-Mode Driver Architecture], kernel.pep_register_component_perf_states, PEP_REGISTER_COMPONENT_PERF_STATES, PPEP_REGISTER_COMPONENT_PERF_STATES, _PEP_REGISTER_COMPONENT_PERF_STATES, PEP_REGISTER_COMPONENT_PERF_STATES structure [Kernel-Mode Driver Architecture], *PPEP_REGISTER_COMPONENT_PERF_STATES
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
-	PEP_REGISTER_COMPONENT_PERF_STATES
product: Windows
targetos: Windows
req.typenames: "*PPEP_REGISTER_COMPONENT_PERF_STATES, PEP_REGISTER_COMPONENT_PERF_STATES"
---

# _PEP_REGISTER_COMPONENT_PERF_STATES structure


## -description


The <b>PEP_REGISTER_COMPONENT_PERF_STATES</b> structure describes the performance states (P-states) of the specified component.


## -syntax


````
typedef struct _PEP_REGISTER_COMPONENT_PERF_STATES {
  PEPHANDLE                DeviceHandle;
  ULONG                    Component;
  ULONGLONG                Flags;
  PPEP_COMPONENT_PERF_INFO PerfStateInfo;
} PEP_REGISTER_COMPONENT_PERF_STATES, *PPEP_REGISTER_COMPONENT_PERF_STATES;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field Flags

[in] A set of input flags. No flag bits are currently defined for this member, which is always zero.


### -field PerfStateInfo

[in] A pointer to a <a href="..\pepfx\ns-pepfx-_pep_component_perf_info.md">PEP_COMPONENT_PERF_INFO</a> structure that contains the performance information for this component's P-states. If this member is non-NULL, it points to P-state information that was supplied by the device driver.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186848">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a> notification. The values of all members of the <b>PEP_REGISTER_COMPONENT_PERF_STATES</b> structure  are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when the notification is sent. The PEP must not write to this structure.

If the <b>PerfStateInfo</b> member is not NULL, the device driver has provided P-state information and requires the PEP to use it.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_component_perf_info.md">PEP_COMPONENT_PERF_INFO</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186848">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_REGISTER_COMPONENT_PERF_STATES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

