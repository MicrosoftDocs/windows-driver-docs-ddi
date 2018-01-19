---
UID: NS:pepfx._PEP_COMPONENT_PLATFORM_CONSTRAINTS
title: _PEP_COMPONENT_PLATFORM_CONSTRAINTS
author: windows-driver-content
description: The PEP_COMPONENT_PLATFORM_CONSTRAINTS structure describes the lowest-powered Fx state of that a component can be in when the platform is in a particular idle state.
old-location: kernel\pep_component_platform_constraints.htm
old-project: kernel
ms.assetid: F7C2DFCC-DB74-4E2E-B252-4897FA320C03
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_COMPONENT_PLATFORM_CONSTRAINTS, *PPEP_COMPONENT_PLATFORM_CONSTRAINTS, PEP_COMPONENT_PLATFORM_CONSTRAINTS
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
req.alt-api: PEP_COMPONENT_PLATFORM_CONSTRAINTS
req.alt-loc: pepfx.h
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
req.typenames: *PPEP_COMPONENT_PLATFORM_CONSTRAINTS, PEP_COMPONENT_PLATFORM_CONSTRAINTS
---

# _PEP_COMPONENT_PLATFORM_CONSTRAINTS structure



## -description
The <b>PEP_COMPONENT_PLATFORM_CONSTRAINTS</b> structure describes the lowest-powered F<i>x</i> state of that a component can be in when the platform is in a particular idle state.



## -syntax

````
typedef struct _PEP_COMPONENT_PLATFORM_CONSTRAINTS {
  PEPHANDLE DeviceHandle;
  ULONG     Component;
  PULONG    MinimumFStates;
  ULONG     PlatformStateCount;
} PEP_COMPONENT_PLATFORM_CONSTRAINTS, *PPEP_COMPONENT_PLATFORM_CONSTRAINTS;
````


## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field MinimumFStates

[in] A pointer to an output buffer. The PEP writes a ULONG array to this buffer that specifies the lowest-powered F<i>x</i> state that  the component can be in for each platform idle state. An element with a value of 0 indicates F0, a value of 1 indicates F1, and so on. If the platform supports M idle states, array elements 0 to M–1 specify the F<i>x</i> states corresponding to platform idle states 0 to M–1.


### -field PlatformStateCount

[in] The number of elements in the <b>MinimumFStates</b> array. The array contains one element for each platform idle state. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) previously sent a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification to the PEP to determine the number of supported platform idle states.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186704">PEP_DPM_COMPONENT_IDLE_CONSTRAINTS</a> notification. All four members of the structure contain input values that PoFx supplies when this notification is sent. PoFx allocates the buffer pointed to by the <b>MinimumFStates</b> member, and the PEP writes to this buffer in response to the notification.


## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186704">PEP_DPM_COMPONENT_IDLE_CONSTRAINTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COMPONENT_PLATFORM_CONSTRAINTS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

