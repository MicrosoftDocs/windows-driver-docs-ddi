---
UID: NF:winddiui.DrvSplDeviceCaps
title: DrvSplDeviceCaps function (winddiui.h)
description: A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities.
old-location: print\drvspldevicecaps.htm
tech.root: print
ms.assetid: 3d129a30-a892-4f4d-b8e3-f277d97980f4
ms.date: 04/20/2018
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

# DrvSplDeviceCaps function


## -description

A printer interface DLL's <b>DrvSplDeviceCaps</b> function queries a printer for its capabilities.

## -parameters

### -param hPrinter

Caller-supplied handle to the printer.

### -param pszDeviceName

### -param Capability

### -param pOutput

### -param cchBufSize

### -param pDevmode

#### - DeviceCap

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
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form that is available for use. 

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PAPERNAMES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form. 

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
</table>
 


#### - cchBuf

Caller-supplied size (in characters) of the buffer pointed to by the <i>pvOutput</i> parameter.


#### - pDM [in, optional]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure that describes the current print job characteristics. If <b>NULL</b>, the function should use the driver's internal default DEVMODEW structure. 


#### - pvOutput [out, optional]

Caller-supplied pointer to a buffer that receives function-supplied information. The buffer's use depends on the value of  the <i>DeviceCap</i> parameter. The caller is responsible for allocating and freeing this buffer. 


#### - pwDeviceName [in]

Caller-supplied pointer to a Unicode string that contains the printer name.

## -returns

The return value depends on the <i>DeviceCap</i> parameter. If <i>DeviceCap</i> indicates a capability that the driver does not support, or if an error is encountered, the function should return GDI_ERROR.

## -remarks

The <b>DrvSplDeviceCaps</b> function is available in Microsoft Windows Server 2003 and later.

For descriptions of the DC_<i>XXX</i> flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a>.

This function must be defined in the .def file as DrvSplDeviceCaps @ 254, because the spooler uses the ordinal number 254 to obtain the driver function pointer.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a>

