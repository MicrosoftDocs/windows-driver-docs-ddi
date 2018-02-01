---
UID: NS:wdm._CM_KEYBOARD_DEVICE_DATA
title: "_CM_KEYBOARD_DEVICE_DATA"
author: windows-driver-content
description: The CM_KEYBOARD_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a keyboard peripheral if the system can collect this information during the boot process.
old-location: kernel\cm_keyboard_device_data.htm
old-project: kernel
ms.assetid: 928cc1b6-4569-4ca1-9410-d864b5556b86
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PCM_KEYBOARD_DEVICE_DATA, wdm/CM_KEYBOARD_DEVICE_DATA, kstruct_a_db7af30d-3698-4c1a-b1ee-9b7e95e7b5fd.xml, CM_KEYBOARD_DEVICE_DATA structure [Kernel-Mode Driver Architecture], PCM_KEYBOARD_DEVICE_DATA, kernel.cm_keyboard_device_data, CM_KEYBOARD_DEVICE_DATA, PCM_KEYBOARD_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], wdm/PCM_KEYBOARD_DEVICE_DATA, _CM_KEYBOARD_DEVICE_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	CM_KEYBOARD_DEVICE_DATA
product: Windows
targetos: Windows
req.typenames: CM_KEYBOARD_DEVICE_DATA, *PCM_KEYBOARD_DEVICE_DATA
req.product: Windows 10 or later.
---

# _CM_KEYBOARD_DEVICE_DATA structure


## -description


The <b>CM_KEYBOARD_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a keyboard peripheral if the system can collect this information during the boot process.


## -syntax


````
typedef struct _CM_KEYBOARD_DEVICE_DATA {
  USHORT Version;
  USHORT Revision;
  UCHAR  Type;
  UCHAR  Subtype;
  USHORT KeyboardFlags;
} CM_KEYBOARD_DEVICE_DATA, *PCM_KEYBOARD_DEVICE_DATA;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>

<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CM_KEYBOARD_DEVICE_DATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

