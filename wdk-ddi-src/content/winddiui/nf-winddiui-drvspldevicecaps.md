---
UID: NF:winddiui.DrvSplDeviceCaps
title: DrvSplDeviceCaps function (winddiui.h)
description: A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities.
tech.root: print
ms.date: 04/19/2022
keywords: ["DrvSplDeviceCaps function"]
ms.keywords: DrvSplDeviceCaps, DrvSplDeviceCaps function [Print Devices], print.drvspldevicecaps, print_interface-graphics_8c345fd4-e513-44ff-94b0-2f035db6a022.xml, winddiui/DrvSplDeviceCaps
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - DrvSplDeviceCaps
 - winddiui/DrvSplDeviceCaps
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvSplDeviceCaps
---

## -description

A printer interface DLL's **DrvSplDeviceCaps** function queries a printer for its capabilities.

## -parameters

### -param hPrinter

Caller-supplied handle to the printer.

### -param pszDeviceName [in]

Caller-supplied pointer to a Unicode string that contains the printer name.

### -param Capability

Caller-supplied bit flag that indicates the capability to query for. (The flags are defined in header file wingdi.h.) This function is not required to support all of the DC_<i>XXX</i> flags, but it must support those listed in the following table.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DC_MEDIAREADY

</td>
<td>
The <i>pOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form that is available for use.

The function's return value should be the number of elements in the returned array.

If <i>pOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PAPERNAMES

</td>
<td>
The <i>pOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form.

The function's return value should be the number of elements in the returned array.

If <i>pOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
</table>

### -param pOutput  [out, optional]

Caller-supplied pointer to a buffer that receives function-supplied information. The buffer's use depends on the value of  the *Capability* parameter. The caller is responsible for allocating and freeing this buffer.

### -param cchBufSize

Caller-supplied size (in characters) of the buffer pointed to by the *pOutput* parameter.

### -param pDevmode  [in, optional]

Caller-supplied pointer to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure that describes the current print job characteristics. If **NULL**, the function should use the driver's internal default DEVMODEW structure.

## -returns

The return value depends on the *Capability* parameter. If *Capability* indicates a capability that the driver does not support, or if an error is encountered, the function should return GDI_ERROR.

## -remarks

For descriptions of the DC_*XXX* flags, see [DrvDeviceCapabilities](./nf-winddiui-drvdevicecapabilities.md).

This function must be defined in the .def file as DrvSplDeviceCaps @ 254, because the spooler uses the ordinal number 254 to obtain the driver function pointer.

## -see-also

[DrvDeviceCapabilities](./nf-winddiui-drvdevicecapabilities.md)