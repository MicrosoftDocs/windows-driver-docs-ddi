---
UID: NS:winddiui._DEVICEPROPERTYHEADER
title: "_DEVICEPROPERTYHEADER"
author: windows-driver-content
description: The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function.
old-location: print\devicepropertyheader.htm
old-project: print
ms.assetid: f1b9cd2f-fa5b-4f34-a237-06d00badf1d1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER structure [Print Devices], PDEVICEPROPERTYHEADER, PDEVICEPROPERTYHEADER structure pointer [Print Devices], _DEVICEPROPERTYHEADER, print.devicepropertyheader, print_interface-graphics_7dc4be04-e0ab-43bb-8e6d-f500cc7cf51c.xml, winddiui/DEVICEPROPERTYHEADER, winddiui/PDEVICEPROPERTYHEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
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
-	winddiui.h
api_name:
-	DEVICEPROPERTYHEADER
product:
- Windows
targetos: Windows
req.typenames: DEVICEPROPERTYHEADER, *PDEVICEPROPERTYHEADER
req.product: Windows 10 or later.
---

# _DEVICEPROPERTYHEADER structure


## -description


The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548542">DrvDevicePropertySheets</a> function.


## -struct-fields




### -field cbSize

Size, in bytes, of the DEVICEPROPERTYHEADER structure.


### -field Flags

Is a set of flags that can be set to the following value: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DPS_NOPERMISSION

</td>
<td>
If set, the user is not permitted to update device settings.

</td>
</tr>
</table>
 


### -field hPrinter

Printer handle.


### -field pszPrinterName

Pointer to a NULL-terminated string representing a printer name.

