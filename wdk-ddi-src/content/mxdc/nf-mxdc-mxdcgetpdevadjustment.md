---
UID: NF:mxdc.MxdcGetPDEVAdjustment
title: MxdcGetPDEVAdjustment function (mxdc.h)
description: The MxdcGetPDEVAdjustment function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC).
old-location: print\mxdcgetpdevadjustment.htm
tech.root: print
ms.assetid: 4839337b-0328-4919-8f49-d7847743845c
ms.date: 04/20/2018
keywords: ["MxdcGetPDEVAdjustment function"]
ms.keywords: MxdcGetPDEVAdjustment, MxdcGetPDEVAdjustment function [Print Devices], mxdc/MxdcGetPDEVAdjustment, print.mxdcgetpdevadjustment, print_xpsdrv_7e324989-1809-44e8-8b5b-c64f83740cd5.xml
f1_keywords:
 - "mxdc/MxdcGetPDEVAdjustment"
 - "MxdcGetPDEVAdjustment"
req.header: mxdc.h
req.include-header: Mxdc.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of the Windows operating system.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mxdc.h
api_name:
- MxdcGetPDEVAdjustment
targetos: Windows
req.typenames: 
---

# MxdcGetPDEVAdjustment function

## -description

The **MxdcGetPDEVAdjustment** function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC).

## -parameters

### -param hPrinter 
[in]
The handle of the currently instantiated printer.

### -param cbDevMode 
[in]
The size of the [DEVMODE](https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew) structure, in bytes, including the driver's private DEVMODE data.

### -param pDevMode 
[in]
A copy of the DEVMODE structure that the MXDC received. The printer interface DLL uses information from this structure to return the requested data.

### -param cbIn 
[in]
An input parameter that designates the size of the *pvIn* parameter, in bytes. This parameter is currently not used and its value is zero.

### -param pvIn 
[in, optional]
A parameter that consists of data that is sent to the printer interface DLL from the MXDC. This parameter is currently not used and its value is **NULL**.

### -param cbPrintPropertiesCollection 
[in]
The size of the [PrintPropertiesCollection](https://docs.microsoft.com/windows-hardware/drivers/print/xps-driver-document-events) data structure, in bytes.

### -param pPrintPropertiesCollection

#### - pOut [in, out]

The **PrintPropertiesCollection** data structure from which the printer interface's DLL gets the requested data. This structure is defined in WinSpool.h. The requested fields might be pre-filled with the MXDC's default data. The printer interface DLL must ignore the fields that it does not understand.

## -returns

**MxdcGetPDEVAdjustment** should return one of the following values:

| Return code | Description |
| --- | --- |
| S_OK | The printer interface DLL successfully returned an adjusted imageable area, compression type, or DPI based on the given DEVMODE structure. The MXDC will validate the returned imageable area and then use it to populate the [GDIINFO](https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-gdiinfo) structure to the respective fields. |
| E_NOTIMPL | The **MxdcGetPDEVAdjustment** function is not implemented by the printer interface. The printer interface must not modify the fields that it does not support. The MXDC defaults to its current defaults. For the imageable area case, MXDC defaults to using the physical page size. For the compression option, MXDC defaults to medium JPEG compression. |
| E_FAIL | For this value or any other failure values, the MXDC returns -1 to the [DrvEnablePDEV](https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenablepdev) function, catches the internal exception, and sets a flag to fail and end the print job. |

## -remarks

The **MxdcGetPDEVAdjustment** function is implemented by the hardware vendor. The MXDC calls this function to obtain printer configuration data in the form of a property bag that includes the following data:

MXDC enables the printer interface DLL to adjust DPI through the **MxdcGetPDEVAdjustment** function only if the print job's **dmPrintQuality** field has a value that is less than or equal to 0. If the DPI value is not adjusted, MXDC maps negative **dmPrintQuality** values to the following resolutions.

| GDI name(Wingdi.h) | GDI value(Wingdi.h) | MXDC default interpretation(dots per inch) |
| --- | --- |
| DMRES_HIGH | -4 | 2400 |
| DMRES_MEDIUM | -3 | 1200 |
| DMRES_LOW | -2 | 600 |
| DMRES_DRAFT | -1 | 400 |

> [!NOTE]
> The name of the MXDC property that stores the MXDC default DPI value is L"MxdcDotsPerInch".

The following table lists the MXDC's property types and property-bag fields for the properties.

<table>
<tr>
<th>Property (propertyName)</th>
<th>Property Type (ePropertyValue)</th>
<th>Property-bag fields</th>
</tr>
<tr>
<td>
L"MxdcImageableArea"

</td>
<td>
kPropertyTypeBuffer

</td>
<td>

PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyBlob.cbBuf = sizeof(RECT)

PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyBlob.pBuf

</td>
</tr>
<tr>
<td>
L"MxdcImageCompressionType"

</td>
<td>
kPropertyTypeInt32

</td>
<td>

PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyInt32

</td>
</tr>
<tr>
<td>
L"MxdcDotsPerInch"

</td>
<td>
kPropertyTypeInt32

</td>
<td>

PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyInt32

</td>
</tr>
<tr>
<td>
L"MxdcLandscapeRotation"

</td>
<td>
kPropertyTypeInt32

</td>
<td>

PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyInt32

</td>
</tr>
</table>

The following table lists the MXDC's supported data types and data values for the properties.

<table>
<tr>
<th>Property (propertyName)</th>
<th>Data types and values</th>
</tr>
<tr>
<td>
L"MxdcImageableArea"

</td>
<td>

Data Type: RECT

Values:

RECT::left (Same as FORM_INFO_1)

RECT::right (Same as FORM_INFO_1)

RECT::top (Same as FORM_INFO_1)

RECT::bottom (Same as FORM_INFO_1)

</td>
</tr>
<tr>
<td>
L"MxdcImageCompressionType"

</td>
<td>

Data Type: LONG

Values:

1 = JPEG High Compression

2 = JPEG Medium Compression

3 = JPEG Low Compression

4 = PNG Compression

</td>
</tr>
<tr>
<td>
L"MxdcDotsPerInch"

</td>
<td>

Data Type: LONG

Values:

A positive value for Dots Per Inch

</td>
</tr>
<tr>
<td>
L"MxdcLandscapeRotation"

</td>
<td>

Data Type: LONG

Values:

90 = MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_90_DEGREES

0 = MXDC_LANDSCAPE_ROTATE_NONE

-90 = MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_270_DEGREES

</td>
</tr>
</table>

> [!NOTE]
>
> The **MxdcGetPDEVAdjustment** function is not a part of the MXDC. The MXDC calls back to this function in the driver's configuration DLL to obtain data for configuring the printer.
>
> The MXDC expects the imageable area to be expressed in unrotated coordinates (portrait orientation). The MXDC rotates both the page size and the imageable area according to the value of the **dmOrientation** member of the DEVMODE structure pointed to by *pDevMode*. Thus, the hardware vendor's implementation of **MxdcGetPDEVAdjustment** should avoid specifying the imageable area in rotated coordinates (landscape orientation) because this will cause landscape print jobs to print incorrectly.
>
> The default value in the MXDC will be MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_270_DEGREES, which is its current legacy behavior.
>
> All rotation will be done on the imageable area. If a configuration component (UniDrv/PostScript, XPSDrv Monolithic) does not understand the new property bag values, then it should ignore them as is in the current design.

## -see-also

[DrvEnablePDEV](https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenablepdev)

[GDIINFO](https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-gdiinfo)

[IPrintOemUIMXDC Interface](https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuimxdc)
