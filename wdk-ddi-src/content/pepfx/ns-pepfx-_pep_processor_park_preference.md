---
UID: NS:pepfx._PEP_PROCESSOR_PARK_PREFERENCE
title: "_PEP_PROCESSOR_PARK_PREFERENCE"
author: windows-driver-content
description: The PEP_PROCESSOR_PARK_PREFERENCE structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption.
old-location: kernel\pep_processor_park_preference.htm
old-project: kernel
ms.assetid: AADA3F1E-DEE8-42E3-B0B8-9EA276F46F86
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_PROCESSOR_PARK_PREFERENCE, PEP_PROCESSOR_PARK_PREFERENCE, PEP_PROCESSOR_PARK_PREFERENCE structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_PARK_PREFERENCE, PPEP_PROCESSOR_PARK_PREFERENCE structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_PARK_PREFERENCE, kernel.pep_processor_park_preference, pepfx/PEP_PROCESSOR_PARK_PREFERENCE, pepfx/PPEP_PROCESSOR_PARK_PREFERENCE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PROCESSOR_PARK_PREFERENCE
product: Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_PARK_PREFERENCE, *PPEP_PROCESSOR_PARK_PREFERENCE
---

# _PEP_PROCESSOR_PARK_PREFERENCE structure


## -description


The <b>PEP_PROCESSOR_PARK_PREFERENCE</b> structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding whether the specified processor should be parked to reduce power consumption.


## -syntax


````
typedef struct _PEP_PROCESSOR_PARK_PREFERENCE {
  PEPHANDLE Processor;
  UCHAR     PoPreference;
  UCHAR     PepPreference;
} PEP_PROCESSOR_PARK_PREFERENCE, *PPEP_PROCESSOR_PARK_PREFERENCE;
````


## -struct-fields




### -field Processor

A <b>PEPHANDLE</b> value that identifies the processor. The PEP supplied this handle in a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field PoPreference

The operating system's parking preference for this processor. For more information, see Remarks.


### -field PepPreference

The PEP's parking preference for this processor. For more information, see Remarks.


## -remarks



The <b>Processors</b> member of the <a href="..\pepfx\ns-pepfx-_pep_ppm_park_selection.md">PEP_PPM_PARK_SELECTION</a> structure is a pointer to an array of <b>PEP_PROCESSOR_PARK_PREFERENCE</b> structures.

The <b>Processor</b> and <b>PoPreference</b> members of the <b>PEP_PROCESSOR_PARK_PREFERENCE</b> structure contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> when a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186812">PEP_NOTIFY_PPM_PARK_SELECTION</a> notification is sent to the PEP. The <b>PepPreference</b> member contains an output value that the PEP writes to the structure in response to this notification.

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

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186812">PEP_NOTIFY_PPM_PARK_SELECTION</a>



<a href="..\pepfx\ns-pepfx-_pep_ppm_park_selection.md">PEP_PPM_PARK_SELECTION</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_PARK_PREFERENCE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

