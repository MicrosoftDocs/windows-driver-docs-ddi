---
UID: NS:pep_x._PEP_PROCESSOR_PARK_PREFERENCE
title: _PEP_PROCESSOR_PARK_PREFERENCE (pep_x.h)
description: The PEP_PROCESSOR_PARK_PREFERENCE structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption.
old-location: kernel\pep_processor_park_preference.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PROCESSOR_PARK_PREFERENCE structure"]
ms.keywords: "*PPEP_PROCESSOR_PARK_PREFERENCE, PEP_PROCESSOR_PARK_PREFERENCE, PEP_PROCESSOR_PARK_PREFERENCE structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_PARK_PREFERENCE, PPEP_PROCESSOR_PARK_PREFERENCE structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_PARK_PREFERENCE, kernel.pep_processor_park_preference, pepfx/PEP_PROCESSOR_PARK_PREFERENCE, pepfx/PPEP_PROCESSOR_PARK_PREFERENCE"
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
targetos: Windows
req.typenames: PEP_PROCESSOR_PARK_PREFERENCE, *PPEP_PROCESSOR_PARK_PREFERENCE
f1_keywords:
 - _PEP_PROCESSOR_PARK_PREFERENCE
 - pep_x/_PEP_PROCESSOR_PARK_PREFERENCE
 - PPEP_PROCESSOR_PARK_PREFERENCE
 - pep_x/PPEP_PROCESSOR_PARK_PREFERENCE
 - PEP_PROCESSOR_PARK_PREFERENCE
 - pep_x/PEP_PROCESSOR_PARK_PREFERENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_PROCESSOR_PARK_PREFERENCE
---

# _PEP_PROCESSOR_PARK_PREFERENCE structure (pep_x.h)


## -description

The <b>PEP_PROCESSOR_PARK_PREFERENCE</b> structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption.

## -struct-fields

### -field Processor

A <b>PEPHANDLE</b> value that identifies the processor. The PEP supplied this handle in a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

### -field PoPreference

The operating system's parking preference for this processor. For more information, see Remarks.

### -field PepPreference

The PEP's parking preference for this processor. For more information, see Remarks.

## -remarks

The <b>Processors</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_park_selection">PEP_PPM_PARK_SELECTION</a> structure is a pointer to an array of <b>PEP_PROCESSOR_PARK_PREFERENCE</b> structures.

The <b>Processor</b> and <b>PoPreference</b> members of the <b>PEP_PROCESSOR_PARK_PREFERENCE</b> structure contain input values that are supplied by the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> when a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_park_selection">PEP_NOTIFY_PPM_PARK_SELECTION</a> notification is sent to the PEP. The <b>PepPreference</b> member contains an output value that the PEP writes to the structure in response to this notification.

The following table lists the three values that are defined for the <b>PoPreference</b> and <b>PepPreference</b> members.

<table>
<tr>
<th>Parking preference</th>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>PROCESSOR_PARK_PREFERENCE_NONE</td>
<td>0x0</td>
<td>No preference. Either parked or unparked is okay.</td>
</tr>
<tr>
<td>PROCESSOR_PARK_PREFERENCE_PARKED</td>
<td>0x1</td>
<td>The operating system or PEP specifies that the processor should be parked.</td>
</tr>
<tr>
<td>PROCESSOR_PARK_PREFERENCE_UNPARKED</td>
<td>0x2</td>
<td>The operating system or PEP specifies that the processor should <u>not</u> be parked.</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_park_selection">PEP_NOTIFY_PPM_PARK_SELECTION</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_park_selection">PEP_PPM_PARK_SELECTION</a>
