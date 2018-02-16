---
UID: NF:winddiui.DrvDeviceCapabilities
title: DrvDeviceCapabilities function
author: windows-driver-content
description: A printer interface DLL's DrvDeviceCapabilities function returns requested information about a printer's capabilities.
old-location: print\drvdevicecapabilities.htm
old-project: print
ms.assetid: a8ea236d-42f9-45c5-b2f6-035e0ba28f75
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: DrvDeviceCapabilities function [Print Devices], print.drvdevicecapabilities, winddiui/DrvDeviceCapabilities, print_interface-graphics_cbe99c7b-a94f-47b2-8c51-d99bdcdec7d3.xml, DrvDeviceCapabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winddiui.h
apiname:
-	DrvDeviceCapabilities
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvDeviceCapabilities function


## -description


A printer interface DLL's <b>DrvDeviceCapabilities</b> function returns requested information about a printer's capabilities.


## -syntax


````
DWORD DrvDeviceCapabilities(
        HANDLE   hPrinter,
  _In_  PWSTR    pDeviceName,
        WORD     iDevCap,
  _Out_ PVOID    pvOutput,
  _In_  PDEVMODE pDevMode
);
````


## -parameters




### -param hPrinter

Caller-supplied printer handle.


### -param pszDeviceName

TBD


### -param Capability

TBD


### -param pOutput

TBD


### -param pDevmode

TBD




#### - iDevCap

Caller-supplied bit flag indicating the information being requested. This can be one of the flags listed in the following table. (The flags are defined in header file Wingdi.h.)

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DC_BINADJUST

</td>
<td>
Not used for NT-based operating systems.

</td>
</tr>
<tr>
<td>
DC_BINNAMES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 24 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a paper source bin.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_BINS

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with a WORD array. Each array element should contain a DMBIN-prefixed constant (or customized value) representing a supported paper source bin.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_COLLATE

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be 1 if the printer supports collating; otherwise, the return value should be zero.

</td>
</tr>
<tr>
<td>
DC_COLORDEVICE

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be 1 if the printer supports color printing; otherwise, the return value should be zero.

</td>
</tr>
<tr>
<td>
DC_COPIES

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the maximum number of copies the printer can support.

</td>
</tr>
<tr>
<td>
DC_DATATYPE_PRODUCED

</td>
<td>
Not used for NT-based operating systems.

</td>
</tr>
<tr>
<td>
DC_DRIVER

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the <b>dmDriverVersion</b> member of the driver's internal <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.

</td>
</tr>
<tr>
<td>
DC_DUPLEX

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be 1 if the printer supports duplex printing; otherwise, the return value should be zero.

</td>
</tr>
<tr>
<td>
DC_EMF_COMPLIANT

</td>
<td>
Not used for NT-based operating systems.

</td>
</tr>
<tr>
<td>
DC_ENUMRESOLUTIONS

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with a LONG array. For each resolution supported by the printer, the function should return two long words (one for the <i>x</i> dimension and one for the <i>y</i> dimension) of the resolution, in dots per inch.

The function's return value should be the number of resolutions supported.

If <b>pvOutput</b> is <b>NULL</b>, the function should just return the number of resolutions supported.

</td>
</tr>
<tr>
<td>
DC_EXTRA

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the <b>dmDriverExtra</b> member of the driver's internal <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.

</td>
</tr>
<tr>
<td>
DC_FIELDS

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the <b>dmFields</b> member of the driver's internal <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. The <b>dmFields</b> member indicates which members in the device-independent portion of the DEVMODEW structure are supported by the printer driver.

</td>
</tr>
<tr>
<td>
DC_FILEDEPENDENCIES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a file that must be installed with the driver.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_MANUFACTURER

</td>
<td>
Not used for NT-based operating systems.

</td>
</tr>
<tr>
<td>
DC_MAXEXTENT

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function should return a POINTS structure (described in the Microsoft Windows SDK documentation). The structure should contain the maximum allowable values for the <b>dmPaperWidth</b> (<i>x</i> dimension) and <b>dmPaperLength</b> (<i>y</i> dimension) members of the printer's DEVMODEW structure.

</td>
</tr>
<tr>
<td>
DC_MEDIAREADY

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a paper form that is available for use.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_MEDIATYPENAMES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a supported media type. 

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should simply return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_MEDIATYPES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with a DWORD array. Each array element should contain a DMMEDIA-prefixed constant (see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure) or customized value representing a supported media type. 

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should simply return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_MINEXTENT

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function should return a POINTS structure (described in the Windows SDK documentation). The structure should contain the minimum allowable values for the <b>dmPaperWidth</b> (<i>x</i> dimension) and <b>dmPaperLength</b> (<i>y</i> dimension) members of the printer's DEVMODEW structure.

</td>
</tr>
<tr>
<td>
DC_MODEL

</td>
<td>
Not used for NT-based operating systems.

</td>
</tr>
<tr>
<td>
DC_NUP

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with a DWORD array. Each array element should contain an integer representing an N-up option (that is, each integer should represent a supported number of document pages per physical page).

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_ORIENTATION

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the number of degrees of rotation required to produce landscape orientation from portrait orientation. A value of zero indicates landscape orientation is not supported.

</td>
</tr>
<tr>
<td>
DC_PAPERNAMES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a paper form.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PAPERS

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with a WORD array. Each array element should contain a DMPAPER-prefixed constant (or customized value) representing a supported paper form.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PAPERSIZE

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with a POINT array. Each array element should contain the <i>x</i> and <i>y</i> dimensions of a form's paper size, in 0.1 mm units, in portrait orientation.

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PERSONALITY

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 32 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the printer description language supported by the printer (for example, L"HP-GL/2").

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PRINTERMEM

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be an integer representing the amount of available printer memory, in kilobytes.

</td>
</tr>
<tr>
<td>
DC_PRINTRATE

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be an integer representing the print rate, in the units specified for DC_PRINTRATEUNIT.

</td>
</tr>
<tr>
<td>
DC_PRINTRATEPPM

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be an integer representing the print rate, in pages per minute.

</td>
</tr>
<tr>
<td>
DC_PRINTRATEUNIT

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should identify the units used for specifying the value returned for DC_PRINTRATE. One of the following constants must be specified: 

PRINTRATEUNIT_PPM - pages/min.

PRINTRATEUNIT_CPS - chars./sec.

PRINTRATEUNIT_LPM - lines/min.

PRINTRATEUNIT_IPM - inches/min.

</td>
</tr>
<tr>
<td>
DC_SIZE

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the <b>dmSize</b> member of the driver's internal <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.

</td>
</tr>
<tr>
<td>
DC_STAPLE

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be <b>TRUE</b> if the printer supports stapling, and <b>FALSE</b> if the printer does not support stapling.

</td>
</tr>
<tr>
<td>
DC_TRUETYPE

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value can be zero, one, or more of the following flags:

DCTT_BITMAP: The device can print TrueType fonts as graphics.

DCTT_DOWNLOAD: The device can accept downloaded TrueType fonts.

DCTT_DOWNLOAD_OUTLINE: (Windows 95/98/Me only) The device can download outline TrueType fonts.

DCTT_SUBDEV: The device can substitute device fonts for TrueType fonts.

</td>
</tr>
<tr>
<td>
DC_VERSION

</td>
<td>
The <i>pvOutput</i> parameter is not used.

The function's return value should be the <b>dmSpecVersion</b> member of the driver's internal <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.

</td>
</tr>
</table>
 


#### - pDevMode [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure that describes the current print job characteristics. If this parameter is <b>NULL</b>, <b>DrvDeviceCapabilities</b> retrieves the current default initialization values for the specified printer driver, such as the user default DEVMODEW structure of the print queue.


#### - pDeviceName [in]

Caller-supplied pointer to a printer name string.


#### - pvOutput [out]

A caller-supplied pointer to a buffer to receive function-supplied information. The buffer's use is dependent on the value received for the <i>iDevCap</i> parameter.


## -returns



The function's return value is dependent on the value received for the <i>iDevCap</i> parameter. If the received <i>iDevCap</i> value represents a capability that the driver does not support, or if an error is encountered, the function should return GDI_ERROR.



