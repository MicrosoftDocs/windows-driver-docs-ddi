---
UID: NF:pepfx.PoFxRegisterCoreDevice
title: PoFxRegisterCoreDevice function (pepfx.h)
description: The PoFxRegisterCoreDevice routine registers a new core system resource with the Windows power management framework (PoFx).
old-location: kernel\pofxregistercoredevice.htm
tech.root: kernel
ms.assetid: D1564DB7-57D9-44B2-8ED2-1170CA4C22EE
ms.date: 04/30/2018
ms.keywords: PoFxRegisterCoreDevice, PoFxRegisterCoreDevice routine [Kernel-Mode Driver Architecture], kernel.pofxregistercoredevice, pepfx/PoFxRegisterCoreDevice
f1_keywords:
 - "pepfx/PoFxRegisterCoreDevice"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ntoskrnl.lib
- ntoskrnl.dll
api_name:
- PoFxRegisterCoreDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxRegisterCoreDevice function


## -description


The <b>PoFxRegisterCoreDevice</b> routine registers a new core system resource with the Windows power management framework (PoFx).


## -parameters




### -param Id [in]

A string that uniquely identifies the core system resource. This member is a pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/install/device-identification-strings">device identification string</a>.


### -param Device [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_po_fx_core_device">PO_FX_CORE_DEVICE</a> structure that describes the power characteristics of the core system resource.


### -param Handle [out]

A pointer to a location to which the routine writes a POHANDLE value. This handle represents the registration of the core system resource with PoFx.


## -returns



<b>PoFxRegisterCoreDevice</b> returns STATUS_SUCCESS if the call successfully registers the PEP. Possible error return values include the following status codes.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The component count for this device is zero, or the <b>PO_FX_CORE_DEVICE</b> structure contains an invalid version number, or the <b>ComponentCriticalTransitionCallback</b> member of this structure contains an invalid function pointer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>
</td>
<td width="60%">
Unable to allocate the resources required to complete the requested registration.

</td>
</tr>
</table>
 




## -remarks



This routine registers a core system resource so that this resource can be power-managed by PoFx.

Core system resources are hardware devices, such as timers and interrupt controllers, that are managed by the Windows hardware abstraction layer (HAL). These devices provide basic functions that are required by the operating system. Due to the close relationship between core system resources and processors, the power management of these resources needs to be coordinated with processor idle state management.

The <b>PoFxRegisterCoreDevice</b> routine should be called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_po_fx_core_device">PO_FX_CORE_DEVICE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

