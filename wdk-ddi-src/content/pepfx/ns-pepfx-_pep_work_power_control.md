---
UID: NS:pepfx._PEP_WORK_POWER_CONTROL
title: _PEP_WORK_POWER_CONTROL (pepfx.h)
description: The PEP_WORK_POWER_CONTROL structure contains the parameters for a power control request that the platform extension plug-in (PEP) sends directly to a processor driver.
old-location: kernel\pep_work_power_control.htm
tech.root: kernel
ms.assetid: 84258422-A2AE-449F-97C8-41336FEA5D8B
ms.date: 04/30/2018
ms.keywords: "*PPEP_WORK_POWER_CONTROL, PEP_WORK_POWER_CONTROL, PEP_WORK_POWER_CONTROL structure [Kernel-Mode Driver Architecture], PPEP_WORK_POWER_CONTROL, PPEP_WORK_POWER_CONTROL structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_POWER_CONTROL, kernel.pep_work_power_control, pepfx/PEP_WORK_POWER_CONTROL, pepfx/PPEP_WORK_POWER_CONTROL"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_WORK_POWER_CONTROL
product:
- Windows
targetos: Windows
req.typenames: PEP_WORK_POWER_CONTROL, *PPEP_WORK_POWER_CONTROL
---

# _PEP_WORK_POWER_CONTROL structure


## -description


The <b>PEP_WORK_POWER_CONTROL</b> structure contains the parameters for a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">power control request</a> that the platform extension plug-in (PEP) sends directly to a processor driver.


## -struct-fields




### -field DeviceHandle

A POHANDLE value that identifies the processor. The PEP received this handle in a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field PowerControlCode

[in] A pointer to a <a href="https://docs.microsoft.com/previous-versions/aa373931(v=vs.80)">GUID</a> value that specifies the power control operation to perform.


### -field RequestContext

A pointer to a PEP-defined context value. The PEP might use this value to uniquely identify a power control request message (in case the PEP issues multiple requests with the same control code to the same device).


### -field InBuffer

[in] A pointer to a driver-allocated input buffer that contains the input parameters for this power control operation.


### -field InBufferSize

[in] The size in bytes of the buffer pointed to by <b>InBuffer</b>.


### -field OutBuffer

[in] A pointer to a driver-allocated output buffer to which the PEP writes the results of this power control operation.


### -field OutBufferSize

[in] The size in bytes of the buffer pointed to by <b>OutBuffer</b>.


## -remarks



The <b>PowerControl</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure is a pointer to a <b>PEP_WORK_POWER_CONTROL</b> structure.

The PEP issues a power control request from a worker thread. The Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">power management framework</a> (PoFx) forwards this request by calling the processor driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a> routine, if the driver implements this routine.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/aa373931(v=vs.80)">GUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a>
 

 

