---
UID: NS:winddiui._DEVICEPROPERTYHEADER
title: _DEVICEPROPERTYHEADER (winddiui.h)
description: The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function.
old-location: print\devicepropertyheader.htm
tech.root: print
ms.assetid: f1b9cd2f-fa5b-4f34-a237-06d00badf1d1
ms.date: 04/20/2018
keywords: ["DEVICEPROPERTYHEADER structure"]
ms.keywords: "*PDEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER structure [Print Devices], PDEVICEPROPERTYHEADER, PDEVICEPROPERTYHEADER structure pointer [Print Devices], _DEVICEPROPERTYHEADER, print.devicepropertyheader, print_interface-graphics_7dc4be04-e0ab-43bb-8e6d-f500cc7cf51c.xml, winddiui/DEVICEPROPERTYHEADER, winddiui/PDEVICEPROPERTYHEADER"
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
targetos: Windows
req.typenames: DEVICEPROPERTYHEADER, *PDEVICEPROPERTYHEADER
f1_keywords:
 - _DEVICEPROPERTYHEADER
 - winddiui/_DEVICEPROPERTYHEADER
 - PDEVICEPROPERTYHEADER
 - winddiui/PDEVICEPROPERTYHEADER
 - DEVICEPROPERTYHEADER
 - winddiui/DEVICEPROPERTYHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DEVICEPROPERTYHEADER
---

# _DEVICEPROPERTYHEADER structure


## -description

The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a> function.

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

