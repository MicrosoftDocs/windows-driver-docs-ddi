---
UID: NS:wdm._D3COLD_SUPPORT_INTERFACE
title: "_D3COLD_SUPPORT_INTERFACE"
author: windows-driver-content
description: The D3COLD_SUPPORT_INTERFACE interface structure contains pointers to the routines in the GUID_D3COLD_SUPPORT_INTERFACE driver interface.
old-location: kernel\d3cold_support_interface.htm
old-project: kernel
ms.assetid: 5B681719-FBCC-417A-9FEB-ACB386FA3BE2
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PD3COLD_SUPPORT_INTERFACE, D3COLD_SUPPORT_INTERFACE, D3COLD_SUPPORT_INTERFACE structure [Kernel-Mode Driver Architecture], PD3COLD_SUPPORT_INTERFACE, PD3COLD_SUPPORT_INTERFACE structure pointer [Kernel-Mode Driver Architecture], _D3COLD_SUPPORT_INTERFACE, kernel.d3cold_support_interface, wdm/D3COLD_SUPPORT_INTERFACE, wdm/PD3COLD_SUPPORT_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	D3COLD_SUPPORT_INTERFACE
product: Windows
targetos: Windows
req.typenames: D3COLD_SUPPORT_INTERFACE, *PD3COLD_SUPPORT_INTERFACE
req.product: Windows 10 or later.
---

# _D3COLD_SUPPORT_INTERFACE structure


## -description


The <b>D3COLD_SUPPORT_INTERFACE</b> interface structure contains pointers to the routines in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967714">GUID_D3COLD_SUPPORT_INTERFACE</a> driver interface.


## -syntax


````
typedef struct _D3COLD_SUPPORT_INTERFACE {
  USHORT                             Size;
  USHORT                             Version;
  PVOID                              Context;
  PINTERFACE_REFERENCE               InterfaceReference;
  PINTERFACE_DEREFERENCE             InterfaceDereference;
  PSET_D3COLD_SUPPORT                SetD3ColdSupport;
  PGET_IDLE_WAKE_INFO                GetIdleWakeInfo;
  PGET_D3COLD_CAPABILITY             GetD3ColdCapability;
  PGET_D3COLD_CAPABILITY             GetBusDriverD3ColdSupport;
  PGET_D3COLD_LAST_TRANSITION_STATUS GetLastTransitionStatus;
} D3COLD_SUPPORT_INTERFACE, *PD3COLD_SUPPORT_INTERFACE;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version. The current version of this interface is D3COLD_SUPPORT_INTERFACE_VERSION.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SetD3ColdSupport

A pointer to a <a href="..\wdm\nc-wdm-set_d3cold_support.md">SetD3ColdSupport</a> routine that enables or disables transitions to the D3cold device power state.


### -field GetIdleWakeInfo

A pointer to a <a href="..\wdm\nc-wdm-get_idle_wake_info.md">GetIdleWakeInfo</a> routine that the device driver calls to discover the device power states from which this device can signal wake events to the processor.


### -field GetD3ColdCapability

A pointer to a <a href="..\wdm\nc-wdm-get_d3cold_capability.md">GetD3ColdCapability</a> routine that reports whether this device is capable of entering the D3cold device power state.


### -field GetBusDriverD3ColdSupport

A pointer to a <a href="..\wdm\nc-wdm-get_d3cold_capability.md">GetBusDriverD3ColdSupport</a> routine that reports whether the underlying bus driver and ACPI system firmware support D3cold for this device.


### -field GetLastTransitionStatus

A pointer to a <a href="..\wdm\nc-wdm-get_d3cold_last_transition_status.md">GetLastTransitionStatus</a> routine that reports whether this device's most recent transition to D3hot was followed by a transition to D3cold.


## -remarks



A device driver that successfully queries for the GUID_D3COLD_SUPPORT_INTERFACE interface receives a pointer to a <b>D3COLD_SUPPORT_INTERFACE</b> structure in which the pointers to the routines in the interface are all non-NULL and valid.

The <b>D3COLD_SUPPORT_INTERFACE</b> structure is an extended version of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.




## -see-also

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



<a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a>



<a href="..\wdm\nc-wdm-get_d3cold_capability.md">GetBusDriverD3ColdSupport</a>



<a href="..\wdm\nc-wdm-set_d3cold_support.md">SetD3ColdSupport</a>



<a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a>



<a href="..\wdm\nc-wdm-get_d3cold_capability.md">GetD3ColdCapability</a>



<a href="..\wdm\nc-wdm-get_d3cold_last_transition_status.md">GetLastTransitionStatus</a>



<a href="..\wdm\nc-wdm-get_idle_wake_info.md">GetIdleWakeInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20D3COLD_SUPPORT_INTERFACE structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

