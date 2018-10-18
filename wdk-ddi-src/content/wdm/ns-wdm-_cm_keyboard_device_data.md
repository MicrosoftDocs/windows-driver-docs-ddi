---
UID: NS:wdm._CM_KEYBOARD_DEVICE_DATA
title: "_CM_KEYBOARD_DEVICE_DATA"
author: windows-driver-content
description: The CM_KEYBOARD_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a keyboard peripheral if the system can collect this information during the boot process.
old-location: kernel\cm_keyboard_device_data.htm
tech.root: kernel
ms.assetid: 928cc1b6-4569-4ca1-9410-d864b5556b86
ms.date: 04/30/2018
ms.keywords: "*PCM_KEYBOARD_DEVICE_DATA, CM_KEYBOARD_DEVICE_DATA, CM_KEYBOARD_DEVICE_DATA structure [Kernel-Mode Driver Architecture], PCM_KEYBOARD_DEVICE_DATA, PCM_KEYBOARD_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_KEYBOARD_DEVICE_DATA, kernel.cm_keyboard_device_data, kstruct_a_db7af30d-3698-4c1a-b1ee-9b7e95e7b5fd.xml, wdm/CM_KEYBOARD_DEVICE_DATA, wdm/PCM_KEYBOARD_DEVICE_DATA"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CM_KEYBOARD_DEVICE_DATA
product:
- Windows
targetos: Windows
req.typenames: CM_KEYBOARD_DEVICE_DATA, *PCM_KEYBOARD_DEVICE_DATA
---

# _CM_KEYBOARD_DEVICE_DATA structure


## -description


The <b>CM_KEYBOARD_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a keyboard peripheral if the system can collect this information during the boot process.


## -struct-fields




### -field Version

The version number of this structure.


### -field Revision

The revision of this structure.


### -field Type

The type of the keyboard.


### -field Subtype

The subtype of the keyboard.


### -field KeyboardFlags

Defined by x86 BIOS INT 16h, function 02 as:

<table>
<tr>
<th>Bit</th>
<th>Defined As</th>
</tr>
<tr>
<td>
7

</td>
<td>
Insert on.

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Caps Lock on.

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Num Lock on.

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Scroll Lock on.

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Alt Key is down.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Ctrl Key is down.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Left shift key is down.

</td>
</tr>
<tr>
<td>
0

</td>
<td>
Right shift key is down.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>
 

 

