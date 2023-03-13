---
UID: NF:winddiui.DrvDeviceCapabilities
title: DrvDeviceCapabilities function (winddiui.h)
description: A printer interface DLL's DrvDeviceCapabilities function returns requested information about a printer's capabilities.
tech.root: print
ms.date: 03/09/2023
keywords: ["DrvDeviceCapabilities function"]
ms.keywords: DrvDeviceCapabilities, DrvDeviceCapabilities function [Print Devices], print.drvdevicecapabilities, print_interface-graphics_cbe99c7b-a94f-47b2-8c51-d99bdcdec7d3.xml, winddiui/DrvDeviceCapabilities
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
 - DrvDeviceCapabilities
 - winddiui/DrvDeviceCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvDeviceCapabilities
---

## -description

A printer interface DLL's **DrvDeviceCapabilities** function returns requested information about a printer's capabilities.

## -parameters

### -param hPrinter

Caller-supplied printer handle.

### -param pszDeviceName [in]

Caller-supplied pointer to a printer name string.

### -param Capability

Caller-supplied bit flag indicating the information being requested. This can be one of the flags listed in the following table. (The flags are defined in header file Wingdi.h.)

| Flag | Definition |
|---|---|
| DC_BINADJUST | Not used for NT-based operating systems. |
| DC_BINNAMES | The *pOutput* parameter points to a buffer that the function should fill with an array of string buffers, each 24 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a paper source bin. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_BINS | The *pOutput* parameter points to a buffer that the function should fill with a WORD array. Each array element should contain a DMBIN-prefixed constant (or customized value) representing a supported paper source bin. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_COLLATE | The *pOutput* parameter is not used. The function's return value should be 1 if the printer supports collating; otherwise, the return value should be zero. |
| DC_COLORDEVICE | The *pOutput* parameter is not used. The function's return value should be 1 if the printer supports color printing; otherwise, the return value should be zero. |
| DC_COPIES | The *pOutput* parameter is not used. The function's return value should be the maximum number of copies the printer can support. |
| DC_DATATYPE_PRODUCED | Not used for NT-based operating systems. |
| DC_DRIVER | The *pOutput* parameter is not used. The function's return value should be the **dmDriverVersion** member of the driver's internal \[DEVMODEW\](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. |
| DC_DUPLEX | The *pOutput* parameter is not used. The function's return value should be 1 if the printer supports duplex printing; otherwise, the return value should be zero. |
| DC_EMF_COMPLIANT | Not used for NT-based operating systems. |
| DC_ENUMRESOLUTIONS | The *pOutput* parameter points to a buffer that the function should fill with a LONG array. For each resolution supported by the printer, the function should return two long words (one for the *x* dimension and one for the *y* dimension) of the resolution, in dots per inch. The function's return value should be the number of resolutions supported. If **pOutput** is **NULL**, the function should just return the number of resolutions supported. |
| DC_EXTRA | The *pOutput* parameter is not used. The function's return value should be the **dmDriverExtra** member of the driver's internal \[DEVMODEW\](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. |
| DC_FIELDS | The *pOutput* parameter is not used. The function's return value should be the **dmFields** member of the driver's internal \[DEVMODEW\](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. The **dmFields** member indicates which members in the device-independent portion of the DEVMODEW structure are supported by the printer driver. |
| DC_FILEDEPENDENCIES | The *pOutput* parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a file that must be installed with the driver. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_MANUFACTURER | Not used for NT-based operating systems. |
| DC_MAXEXTENT | The *pOutput* parameter is not used. The function should return a POINTS structure (described in the Microsoft Windows SDK documentation). The structure should contain the maximum allowable values for the **dmPaperWidth** (*x* dimension) and **dmPaperLength** (*y* dimension) members of the printer's DEVMODEW structure. |
| DC_MEDIAREADY | The *pOutput* parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a paper form that is available for use. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_MEDIATYPENAMES | The *pOutput* parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a supported media type. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should simply return the number of array elements required. |
| DC_MEDIATYPES | The *pOutput* parameter points to a buffer that the function should fill with a DWORD array. Each array element should contain a DMMEDIA-prefixed constant (see the \[DEVMODEW\](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure) or customized value representing a supported media type. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should simply return the number of array elements required. |
| DC_MINEXTENT | The *pOutput* parameter is not used. The function should return a POINTS structure (described in the Windows SDK documentation). The structure should contain the minimum allowable values for the **dmPaperWidth** (*x* dimension) and **dmPaperLength** (*y* dimension) members of the printer's DEVMODEW structure. |
| DC_MODEL | Not used for NT-based operating systems. |
| DC_NUP | The *pOutput* parameter points to a buffer that the function should fill with a DWORD array. Each array element should contain an integer representing an N-up option (that is, each integer should represent a supported number of document pages per physical page). The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_ORIENTATION | The *pOutput* parameter is not used. The function's return value should be the number of degrees of rotation required to produce landscape orientation from portrait orientation. A value of zero indicates landscape orientation is not supported. |
| DC_PAPERNAMES | The *pOutput* parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the name of a paper form. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_PAPERS | The *pOutput* parameter points to a buffer that the function should fill with a WORD array. Each array element should contain a DMPAPER-prefixed constant (or customized value) representing a supported paper form. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_PAPERSIZE | The *pOutput* parameter points to a buffer that the function should fill with a POINT array. Each array element should contain the *x* and *y* dimensions of a form's paper size, in 0.1 mm units, in portrait orientation. The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_PERSONALITY | The *pOutput* parameter points to a buffer that the function should fill with an array of string buffers, each 32 characters in length. Each string buffer in the array should contain a wide-character, NULL-terminated string specifying the printer description language supported by the printer (for example, L"HP-GL/2"). The function's return value should be the number of elements in the returned array. If *pOutput* is **NULL**, the function should just return the number of array elements required. |
| DC_PRINTERMEM | The *pOutput* parameter is not used. The function's return value should be an integer representing the amount of available printer memory, in kilobytes. |
| DC_PRINTRATE | The *pOutput* parameter is not used. The function's return value should be an integer representing the print rate, in the units specified for DC_PRINTRATEUNIT. |
| DC_PRINTRATEPPM | The *pOutput* parameter is not used. The function's return value should be an integer representing the print rate, in pages per minute. |
| DC_PRINTRATEUNIT | The *pOutput* parameter is not used. The function's return value should identify the units used for specifying the value returned for DC_PRINTRATE. One of the following constants must be specified: PRINTRATEUNIT_PPM - pages/min. PRINTRATEUNIT_CPS - chars./sec. PRINTRATEUNIT_LPM - lines/min. PRINTRATEUNIT_IPM - inches/min. |
| DC_SIZE | The *pOutput* parameter is not used. The function's return value should be the **dmSize** member of the driver's internal \[DEVMODEW\](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. |
| DC_STAPLE | The *pOutput* parameter is not used. The function's return value should be **TRUE** if the printer supports stapling, and **FALSE** if the printer does not support stapling. |
| DC_TRUETYPE | The *pOutput* parameter is not used. The function's return value can be zero, one, or more of the following flags: DCTT_BITMAP: The device can print TrueType fonts as graphics. DCTT_DOWNLOAD: The device can accept downloaded TrueType fonts. DCTT_DOWNLOAD_OUTLINE: (Windows 95/98/Me only) The device can download outline TrueType fonts. DCTT_SUBDEV: The device can substitute device fonts for TrueType fonts. |
| DC_VERSION | The *pOutput* parameter is not used. The function's return value should be the **dmSpecVersion** member of the driver's internal \[DEVMODEW\](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. |

### -param pOutput [out]

A caller-supplied pointer to a buffer to receive function-supplied information. The buffer's use is dependent on the value received for the *Capability* parameter.

### -param pDevmode [in, optional]

A caller-supplied pointer to a [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure that describes the current print job characteristics. If this parameter is **NULL**, **DrvDeviceCapabilities** retrieves the current default initialization values for the specified printer driver, such as the user default DEVMODEW structure of the print queue.

## -returns

The function's return value is dependent on the value received for the *Capability* parameter. If the received *Capability* value represents a capability that the driver does not support, or if an error is encountered, the function should return GDI_ERROR.
