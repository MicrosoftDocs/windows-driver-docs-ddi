---
UID: NS:pep_x._PEP_POWER_CONTROL_COMPLETE
title: _PEP_POWER_CONTROL_COMPLETE (pep_x.h)
description: The PEP_POWER_CONTROL_COMPLETE structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed.
old-location: kernel\pep_power_control_complete.htm
tech.root: kernel
ms.assetid: E270B609-2D47-4D55-94A6-BE82B2E5B77A
ms.date: 04/30/2018
ms.keywords: "*PPEP_POWER_CONTROL_COMPLETE, PEP_POWER_CONTROL_COMPLETE, PEP_POWER_CONTROL_COMPLETE structure [Kernel-Mode Driver Architecture], PPEP_POWER_CONTROL_COMPLETE, PPEP_POWER_CONTROL_COMPLETE structure pointer [Kernel-Mode Driver Architecture], _PEP_POWER_CONTROL_COMPLETE, kernel.pep_power_control_complete, pepfx/PEP_POWER_CONTROL_COMPLETE, pepfx/PPEP_POWER_CONTROL_COMPLETE"
f1_keywords:
 - "pep_x/PEP_POWER_CONTROL_COMPLETE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_POWER_CONTROL_COMPLETE
product:
- Windows
targetos: Windows
req.typenames: PEP_POWER_CONTROL_COMPLETE, *PPEP_POWER_CONTROL_COMPLETE
---

# _PEP_POWER_CONTROL_COMPLETE structure


## -description


The <b>PEP_POWER_CONTROL_COMPLETE</b> structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field PowerControlCode

[in] A pointer to a <a href="https://docs.microsoft.com/previous-versions/aa373931(v=vs.80)">GUID</a> value that specifies the power control operation that was performed. This is the same value that the PEP supplied in response to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification to initiate the power control operation.


### -field RequestContext

[in] A pointer to the request context that was sent by the PEP in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure that the PEP supplied in the original work request. Typically, this member points to a structure that contains a pointer to an output buffer to contain the results of the power control operation that was requested by the PEP.


### -field BytesReturned

[in] The size, in bytes, of the result data stored by the driver in the output buffer. For more information about this buffer, see the description of the <b>RequestContext</b> member.


### -field Status

[in] The status of the power control operation. If the operation was successful, the PEP sets this member to STATUS_SUCCESS. Otherwise, the PEP sets this member to an appropriate error status code.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_power_control_complete">PEP_DPM_POWER_CONTROL_COMPLETE</a> notification. All five members of the structure contain input values that are supplied by

If the output buffer is too small to receive all of the result data from the operation, the PEP sets the <b>Status</b> member of the structure to STATUS_INSUFFICIENT_RESOURCES, sets  the <b>BytesReturned</b> member to the required size of the output buffer, and (typically) writes no data to the output buffer.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/aa373931(v=vs.80)">GUID</a>
 

 

