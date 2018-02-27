---
UID: NF:mxdc.MxdcGetPDEVAdjustment
title: MxdcGetPDEVAdjustment function
author: windows-driver-content
description: The MxdcGetPDEVAdjustment function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC).
old-location: print\mxdcgetpdevadjustment.htm
old-project: print
ms.assetid: 4839337b-0328-4919-8f49-d7847743845c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: MxdcGetPDEVAdjustment, MxdcGetPDEVAdjustment function [Print Devices], mxdc/MxdcGetPDEVAdjustment, print.mxdcgetpdevadjustment, print_xpsdrv_7e324989-1809-44e8-8b5b-c64f83740cd5.xml
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
-	mxdc.h
apiname:
-	MxdcGetPDEVAdjustment
product: Windows
targetos: Windows
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


### -param pPrintPropertiesCollection

TBD




#### - pOut [in, out]

The <b>PrintPropertiesCollection</b> data structure from which the printer interface's DLL gets the requested data. This structure is defined in WinSpool.h. The requested fields might be pre-filled with the MXDC's default data. The printer interface DLL must ignore the fields that it does not understand.


## -returns



<code>MxdcGetPDEVAdjustment</code> should return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The printer interface DLL successfully returned an adjusted imageable area, compression type, or DPI based on the given DEVMODE structure. The MXDC will validate the returned imageable area and then use it to populate the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566484">GDIINFO</a> structure to the respective fields.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The <code>MxdcGetPDEVAdjustment</code> function is not implemented by the printer interface. The printer interface must not modify the fields that it does not support. The MXDC defaults to its current defaults. For the imageable area case, MXDC defaults to using the physical page size. For the compression option, MXDC defaults to medium JPEG compression.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
For this value or any other failure values, the MXDC returns -1 to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a> function, catches the internal exception, and sets a flag to fail and end the print job.

</td>
</tr>
</table>
 




## -remarks



The <code>MxdcGetPDEVAdjustment</code> function is implemented by the hardware vendor. The MXDC calls this function to obtain printer configuration data in the form of a <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">property bag</a> that includes the following data:



MXDC enables the printer interface DLL to adjust DPI through the <code>MxdcGetPDEVAdjustment</code> function only if the print job's <b>dmPrintQuality</b> field has a value that is less than or equal to 0. If the DPI value is not adjusted, MXDC maps negative <b>dmPrintQuality</b> values to the following resolutions.

<table>
<tr>
<th>GDI name(Wingdi.h)</th>
<th>GDI value(Wingdi.h)</th>
<th>MXDC default interpretation(dots per inch)</th>
</tr>
<tr>
<td>
DMRES_HIGH

</td>
<td>
-4

</td>
<td>
2400

</td>
</tr>
<tr>
<td>
DMRES_MEDIUM

</td>
<td>
-3

</td>
<td>
1200

</td>
</tr>
<tr>
<td>
DMRES_LOW

</td>
<td>
-2

</td>
<td>
600

</td>
</tr>
<tr>
<td>
DMRES_DRAFT

</td>
<td>
-1

</td>
<td>
400

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  The name of the MXDC property that stores the MXDC default DPI value is L"MxdcDotsPerInch". </div>
<div> </div>
The following table lists the MXDC's property types and property-bag fields for the properties.

<table>
<tr>
<th>Property(propertyName)</th>
<th>Property Type(ePropertyValue)</th>
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
<th>Property(propertyName)</th>
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

<dl>
<dd>90 = MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_90_DEGREES</dd>
<dd>0 = MXDC_LANDSCAPE_ROTATE_NONE</dd>
<dd>-90 = MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_270_DEGREES</dd>
</dl>
</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  <b>Notes</b><ul>
<li>
The <code>MxdcGetPDEVAdjustment</code> function is not a part of the MXDC. The MXDC calls back to this function in the driver's configuration DLL to obtain data for configuring the printer.

</li>
<li>
The MXDC expects the imageable area to be expressed in unrotated coordinates (portrait orientation). The MXDC rotates both the page size and the imageable area according to the value of the <b>dmOrientation</b> member of the DEVMODE structure pointed to by <i>pDevMode</i>. Thus, the hardware vendor's implementation of <code>MxdcGetPDEVAdjustment</code> should avoid specifying the imageable area in rotated coordinates (landscape orientation) because this will cause landscape print jobs to print incorrectly.

</li>
<li>
The default value in the MXDC will be MXDC_LANDSCAPE_ROTATE_COUNTERCLOCKWISE_270_DEGREES, which is its current legacy behavior.

All rotation will be done on the imageable area. If a configuration component (UniDrv/PostScript, XPSDrv Monolithic) does not understand the new property bag values, then it should ignore them as is in the current design.

</li>
</ul>
</div>
<div> </div>



## -see-also

<a href="..\prcomoem\nn-prcomoem-iprintoemuimxdc.md">IPrintOemUIMXDC Interface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566484">GDIINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MxdcGetPDEVAdjustment function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

