---
UID: NS:wdm._D3COLD_SUPPORT_INTERFACE
title: _D3COLD_SUPPORT_INTERFACE (wdm.h)
description: The D3COLD_SUPPORT_INTERFACE interface structure contains pointers to the routines in the GUID_D3COLD_SUPPORT_INTERFACE driver interface.
old-location: kernel\d3cold_support_interface.htm
tech.root: kernel
ms.assetid: 5B681719-FBCC-417A-9FEB-ACB386FA3BE2
ms.date: 04/30/2018
keywords: ["_D3COLD_SUPPORT_INTERFACE structure"]
ms.keywords: "*PD3COLD_SUPPORT_INTERFACE, D3COLD_SUPPORT_INTERFACE, D3COLD_SUPPORT_INTERFACE structure [Kernel-Mode Driver Architecture], PD3COLD_SUPPORT_INTERFACE, PD3COLD_SUPPORT_INTERFACE structure pointer [Kernel-Mode Driver Architecture], _D3COLD_SUPPORT_INTERFACE, kernel.d3cold_support_interface, wdm/D3COLD_SUPPORT_INTERFACE, wdm/PD3COLD_SUPPORT_INTERFACE"
f1_keywords:
 - "wdm/D3COLD_SUPPORT_INTERFACE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- D3COLD_SUPPORT_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: D3COLD_SUPPORT_INTERFACE, *PD3COLD_SUPPORT_INTERFACE
---

# _D3COLD_SUPPORT_INTERFACE structure


## -description


The <b>D3COLD_SUPPORT_INTERFACE</b> interface structure contains pointers to the routines in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967714">GUID_D3COLD_SUPPORT_INTERFACE</a> driver interface.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version. The current version of this interface is D3COLD_SUPPORT_INTERFACE_VERSION.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SetD3ColdSupport

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-set_d3cold_support">SetD3ColdSupport</a> routine that enables or disables transitions to the D3cold device power state.


### -field GetIdleWakeInfo

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_idle_wake_info">GetIdleWakeInfo</a> routine that the device driver calls to discover the device power states from which this device can signal wake events to the processor.


### -field GetD3ColdCapability

A pointer to a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh967711(v=vs.85)">GetD3ColdCapability</a> routine that reports whether this device is capable of entering the D3cold device power state.


### -field GetBusDriverD3ColdSupport

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_d3cold_capability">GetBusDriverD3ColdSupport</a> routine that reports whether the underlying bus driver and ACPI system firmware support D3cold for this device.


### -field GetLastTransitionStatus

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_d3cold_last_transition_status">GetLastTransitionStatus</a> routine that reports whether this device's most recent transition to D3hot was followed by a transition to D3cold.


## -remarks



A device driver that successfully queries for the GUID_D3COLD_SUPPORT_INTERFACE interface receives a pointer to a <b>D3COLD_SUPPORT_INTERFACE</b> structure in which the pointers to the routines in the interface are all non-NULL and valid.

The <b>D3COLD_SUPPORT_INTERFACE</b> structure is an extended version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_d3cold_capability">GetBusDriverD3ColdSupport</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh967711(v=vs.85)">GetD3ColdCapability</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_idle_wake_info">GetIdleWakeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_d3cold_last_transition_status">GetLastTransitionStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-set_d3cold_support">SetD3ColdSupport</a>
 

 

