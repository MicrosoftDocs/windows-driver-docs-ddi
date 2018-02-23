---
UID: NS:pepfx._PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
title: "_PEP_QUERY_CURRENT_COMPONENT_PERF_STATE"
author: windows-driver-content
description: The PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure contains information about the current P-state in the specified P-state set.
old-location: kernel\pep_query_current_component_perf_state.htm
old-project: kernel
ms.assetid: 2A561853-B809-4BF5-911C-520A7D9C473C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE, PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure [Kernel-Mode Driver Architecture], kernel.pep_query_current_component_perf_state, *PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE, pepfx/PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE, PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, pepfx/PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
product: Windows
targetos: Windows
req.typenames: PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, *PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE
---

# _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure


## -description


The <b>PEP_QUERY_CURRENT_COMPONENT_PERF_STATE</b> structure contains information about the current P-state in the specified P-state set.


## -syntax


````
typedef struct _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE {
  PEPHANDLE DeviceHandle;
  ULONG     Component;
  ULONG     Set;
  union {
    ULONG     StateIndex;
    ULONGLONG StateValue;
  };
} PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, *PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field Set

[in] The index that identifies this P-state set. If M is the number of P-state sets for this component, P-state set indexes range from 0 to M–1. The PEP previously specified the number of P-state sets in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186839">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification.


#### - ( unnamed union )

The current performance level of this P-state set expressed either as an index into a set of discrete values or as a value in a range. In response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186840">PEP_DPM_QUERY_COMPONENT_PERF_SET</a> notification, the PEP indicated whether the performance values in the P-state set are of type <b>PoFxPerfStateTypeDiscrete</b> or <b>PoFxPerfStateTypeRange</b>.



#### StateIndex

[out] The index of the current P-state for the specified P-state set. Write to this member if the performance values for the P-state set are of type <b>PoFxPerfStateTypeDiscrete</b>.



#### StateValue

[out] The value of the current P-state for the specified P-state set. Write to this member if the performance values for the P-state set are of type <b>PoFxPerfStateTypeRange</b>.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186843">PEP_DPM_QUERY_CURRENT_COMPONENT_PERF_STATE</a> notification. The <b>DeviceHandle</b>, <b>Component</b>, and <b>Set</b> members contain input values supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent. The <b>StateIndex</b> member or <b>StateValue</b> member contains an output value that the PEP writes to the structure in response to the notification.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186843">PEP_DPM_QUERY_CURRENT_COMPONENT_PERF_STATE</a>



<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

