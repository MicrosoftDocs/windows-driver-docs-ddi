---
UID: NF:mxdc.MxdcGetPDEVAdjustment
title: MxdcGetPDEVAdjustment function
author: windows-driver-content
description: The MxdcGetPDEVAdjustment function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC).
old-location: print\mxdcgetpdevadjustment.htm
old-project: print
ms.assetid: 4839337b-0328-4919-8f49-d7847743845c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: MxdcGetPDEVAdjustment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mxdc.h
req.include-header: Mxdc.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MxdcGetPDEVAdjustment
req.alt-loc: mxdc.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MxdcGetPDEVAdjustment function



## -description
The <code>MxdcGetPDEVAdjustment</code> function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC).



## -syntax

````
HRESULT MxdcGetPDEVAdjustment(
  _In_           HANDLE                    hPrinter,
  _In_           ULONG                     cbDevMode,
  _In_     const DEVMODE                   *pDevMode,
  _In_           ULONG                     cbIn,
  _In_opt_ const VOID                      *pvIn,
  _In_           ULONG                     cbPrintPropertiesCollection,
  _Inout_        PrintPropertiesCollection *pOut
);
````


## -parameters

### -param hPrinter [in]

The handle of the currently instantiated printer.


### -param cbDevMode [in]

The size of the <a href="https://msdn.microsoft.com/b2369876-9a79-40c8-8d27-c8b9d8e68e6b">DEVMODE</a> structure, in bytes, including the driver's private DEVMODE data.


### -param pDevMode [in]

A copy of the DEVMODE structure that the MXDC received. The printer interface DLL uses information from this structure to return the requested data.


### -param cbIn [in]

An input parameter that designates the size of the <i>pvIn</i> parameter, in bytes. This parameter is currently not used and its value is zero.


### -param pvIn [in, optional]

A parameter that consists of data that is sent to the printer interface DLL from the MXDC. This parameter is currently not used and its value is <b>NULL</b>.


### -param cbPrintPropertiesCollection [in]

The size of the <a href="https://msdn.microsoft.com/240e14d1-d8ee-403c-b728-b14941775634">PrintPropertiesCollection</a> data structure, in bytes.


### -param pOut [in, out]

The <b>PrintPropertiesCollection</b> data structure from which the printer interface's DLL gets the requested data. This structure is defined in WinSpool.h. The requested fields might be pre-filled with the MXDC's default data. The printer interface DLL must ignore the fields that it does not understand.


## -returns
<code>MxdcGetPDEVAdjustment</code> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The printer interface DLL successfully returned an adjusted imageable area, compression type, or DPI based on the given DEVMODE structure. The MXDC will validate the returned imageable area and then use it to populate the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566484">GDIINFO</a> structure to the respective fields.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The <code>MxdcGetPDEVAdjustment</code> function is not implemented by the printer interface. The printer interface must not modify the fields that it does not support. The MXDC defaults to its current defaults. For the imageable area case, MXDC defaults to using the physical page size. For the compression option, MXDC defaults to medium JPEG compression.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>For this value or any other failure values, the MXDC returns -1 to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a> function, catches the internal exception, and sets a flag to fail and end the print job.

 


## -remarks
The <code>MxdcGetPDEVAdjustment</code> function is implemented by the hardware vendor. The MXDC calls this function to obtain printer configuration data in the form of a <a href="wdkgloss.p#wdkgloss.property_bag#wdkgloss.property_bag"><i>property bag</i></a> that includes the following data:



The corner coordinates of the area in which a printer can lay down ink, as determined by the design of the printer and the selected paper size.

The file format of an image, either JPEG or PNG, and the level of compression for JPEG images.

The resolution of an image in dots per inch (DPI). If the printer interface DLL does not support this field, MXDC defaults to a device-independent resolution that the <b>dmPrintQuality</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure sets.

MXDC enables the printer interface DLL to adjust DPI through the <code>MxdcGetPDEVAdjustment</code> function only if the print job's <b>dmPrintQuality</b> field has a value that is less than or equal to 0. If the DPI value is not adjusted, MXDC maps negative <b>dmPrintQuality</b> values to the following resolutions.

DMRES_HIGH

-4

2400

DMRES_MEDIUM

-3

1200

DMRES_LOW

-2

600

DMRES_DRAFT

-1

400

The following table lists the MXDC's property types and property-bag fields for the properties.

L"MxdcImageableArea"

kPropertyTypeBuffer


        PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyBlob.cbBuf = sizeof(RECT)
       


        PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyBlob.pBuf
       

L"MxdcImageCompressionType"

kPropertyTypeInt32


        PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyInt32
       

L"MxdcDotsPerInch"

L"MxdcLandscapeRotation" 


        PrintPropertiesCollection::propertiesCollection[i].propertyValue.value.propertyInt32 
       

The following table lists the MXDC's supported data types and data values for the properties.


        Data Type: RECT


        Values:

RECT::left (Same as FORM_INFO_1)

RECT::right (Same as FORM_INFO_1)

RECT::top (Same as FORM_INFO_1)

RECT::bottom (Same as FORM_INFO_1)


        Data Type: LONG

1 = JPEG High Compression

2 = JPEG Medium Compression

3 = JPEG Low Compression

4 = PNG Compression


        Values: 

A positive value for Dots Per Inch


        Data Type: LONG 

Values:

The <code>MxdcGetPDEVAdjustment</code> function is not a part of the MXDC. The MXDC calls back to this function in the driver's configuration DLL to obtain data for configuring the printer.

The MXDC expects the imageable area to be expressed in unrotated coordinates (portrait orientation). The MXDC rotates both the page size and the imageable area according to the value of the <b>dmOrientation</b> member of the DEVMODE structure pointed to by <i>pDevMode</i>. Thus, the hardware vendor's implementation of <code>MxdcGetPDEVAdjustment</code> should avoid specifying the imageable area in rotated coordinates (landscape orientation) because this will cause landscape print jobs to print incorrectly.

The default value in the MXDC will be MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_270_DEGREES, which is its current legacy behavior.

All rotation will be done on the imageable area. If a configuration component (UniDrv/PostScript, XPSDrv Monolithic) does not understand the new property bag values, then it should ignore them as is in the current design.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566484">GDIINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554157">IPrintOemUIMXDC Interface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MxdcGetPDEVAdjustment function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

