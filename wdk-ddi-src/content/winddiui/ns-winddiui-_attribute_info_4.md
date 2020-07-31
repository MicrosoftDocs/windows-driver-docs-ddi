---
UID: NS:winddiui._ATTRIBUTE_INFO_4
title: _ATTRIBUTE_INFO_4 (winddiui.h)
description: The ATTRIBUTE_INFO_4 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function.
old-location: print\attribute_info_4.htm
tech.root: print
ms.assetid: 09071fff-834b-452b-ae1e-b75c9f191b15
ms.date: 04/20/2018
keywords: ["_ATTRIBUTE_INFO_4 structure"]
ms.keywords: "*PATTRIBUTE_INFO_4, ATTRIBUTE_INFO_4, ATTRIBUTE_INFO_4 structure [Print Devices], PATTRIBUTE_INFO_4, PATTRIBUTE_INFO_4 structure pointer [Print Devices], _ATTRIBUTE_INFO_4, print.attribute_info_4, print_interface-graphics_7fa07014-1d16-48c0-be12-cb5026d8f285.xml, winddiui/ATTRIBUTE_INFO_4, winddiui/PATTRIBUTE_INFO_4"
f1_keywords:
 - "winddiui/ATTRIBUTE_INFO_4"
 - "ATTRIBUTE_INFO_4"
req.header: winddiui.h
req.include-header: Winddiui.h, Winsplp.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winddiui.h
api_name:
- ATTRIBUTE_INFO_4
targetos: Windows
req.typenames: ATTRIBUTE_INFO_4, *PATTRIBUTE_INFO_4
---

# _ATTRIBUTE_INFO_4 structure


## -description


The ATTRIBUTE_INFO_4 structure is used as a parameter for a printer interface DLL's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> function. All member values are function-supplied. This structure is similar to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3">ATTRIBUTE_INFO_3</a>, but it includes additional members to control N-up, duplex and booklet printing, and scaling.


## -struct-fields




### -field dwJobNumberOfPagesPerSide

Number of document pages to be placed on one side of a physical page, as requested by the user. Allowable values are 1, 2, 4, 6, 9, or 16.


### -field dwDrvNumberOfPagesPerSide

Number of document pages that the printer and driver can place on one side of a physical page. This value must be 1 or the value specified for <b>dwJobNumberOfPagesPerSide</b>.


### -field dwNupBorderFlags

One of the following bit flag values:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
BORDER_PRINT

</td>
<td>
The print processor should draw a border around the page.

</td>
</tr>
<tr>
<td>
NO_BORDER_PRINT

</td>
<td>
The print processor should not draw a border around the page.

</td>
</tr>
</table>
 


### -field dwJobPageOrderFlags

One of the following bit flag values:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
BOOKLET_PRINT

</td>
<td>
Pages should be printed in booklet form, with two document pages printed on one side of a physical page. In landscape mode, the two document pages are printed side-by-side on the paper. In portrait mode, the two document pages are printed top-and-bottom.

</td>
</tr>
<tr>
<td>
NORMAL_PRINT

</td>
<td>
Pages should be printed in normal order: page 1, page 2, and so on.

</td>
</tr>
<tr>
<td>
REVERSE_PRINT

</td>
<td>
Pages should be printed in reverse order: last page, next-to-last page, and so on.

</td>
</tr>
</table>
 


### -field dwDrvPageOrderFlags

Bit flags indicating which page ordering options are supported by the printer and driver. Uses the same flags as <b>dwJobPageOrderFlags</b>.


### -field dwJobNumberOfCopies

Number of copies of the print job, as requested by the user.


### -field dwDrvNumberOfCopies

Maximum number of copies the printer and driver can handle at once, taking into account such job attributes as collating and stapling.


### -field dwColorOptimization

One of the following bit flag values:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
COLOR_OPTIMIZATION

</td>
<td>
The print processor should use monochrome color optimization.

</td>
</tr>
<tr>
<td>
NO_COLOR_OPTIMIZATION

</td>
<td>
The print processor should not use monochrome color optimization.

</td>
</tr>
</table>
 


### -field dmPrintQuality

Value to be used instead of the <b>dmPrintQuality</b> member of the print job's <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure, if the COLOR_OPTIMIZATION flag is set in <b>dwColorOptimization</b>.


### -field dmYResolution

Value to be used instead of the <b>dmYResolution</b> member of the print job's DEVMODEW structure, if the COLOR_OPTIMIZATION flag is set in <b>dwColorOptimization</b>.
     


### -field dwDuplexFlags

One of the following bit flag values used in duplex printing:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DONT_SEND_EXTRA_PAGES_FOR_DUPLEX

</td>
<td>
The print processor should not send extra blank pages when duplex printing.

For example, if you send a three-page job for duplex printing, some printers expect to receive four pages. If you print this job on Microsoft Windows XP or Windows Server 2003, the print processor sends four pages to the printer by default (the fourth page is a blank page). If you print this job on Windows Vista with this flag set, the print processor sends only the three pages of the print job and does not send the extra blank page.

</td>
</tr>
<tr>
<td>
REVERSE_PAGES_FOR_REVERSE_DUPLEX

</td>
<td>
The print processor should reverse the order of page pairs when printing in reverse duplex mode. For example, when this flag is set, the print processor should print pages in order 7, 8, 5, 6, 3, 4, 1, 2 instead of 8, 7, 6, 5, 4, 3, 2, 1.

</td>
</tr>
</table>
 

Set to 0 if your driver does not require any of these options.


### -field dwNupDirection

One of the following bit flag values used in N-up printing:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
RIGHT_THEN_DOWN

</td>
<td>
The print processor should provide page images in sequence from left to right, then down the final printed page. Also set to this value if N-up printing is not needed.

</td>
</tr>
<tr>
<td>
DOWN_THEN_RIGHT

</td>
<td>
The print processor should provide page images in sequence from top to bottom, then left to right on the final printed page.

</td>
</tr>
<tr>
<td>
LEFT_THEN_DOWN

</td>
<td>
The print processor should provide page images in sequence from right to left, then down the final printed page.

</td>
</tr>
<tr>
<td>
DOWN_THEN_LEFT

</td>
<td>
The print processor should provide page images in sequence from top to bottom, then right to left on the final printed page.

</td>
</tr>
</table>
 

This flag is considered only if <b>dwJobNumberOfPagesPerSide</b> and/or <b>dwDrvNumberOfPagesPerSide</b> indicate that N-up printing is active. For more information, see the descriptions  above for <b>dwJobNumberOfPagesPerSide</b> and <b>dwDrvNumberOfPagesPerSide</b>.


### -field dwBookletFlags

If <b>dwJobPageOrderFlags</b> is set to BOOKLET_PRINT, one of the following values. 

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
BOOKLET_EDGE_LEFT

</td>
<td>
The print processor should print pages in a left-to-right booklet layout, where the bound edge of the final folded booklet is on the left edge of page one.

</td>
</tr>
<tr>
<td>
BOOKLET_EDGE_RIGHT

</td>
<td>
The print processor should print pages in a right-to-left booklet layout, where the bound edge of the final folded booklet is on the right edge of page one.

</td>
</tr>
</table>
 

If <b>dwJobPageOrderFlags</b> is not set to BOOKLET_PRINT, <b>dwBookletFlags </b>is set to 0.

This flag is considered only if the <b>dwJobPageOrderFlags</b> member is set to BOOKLET_PRINT.


### -field dwScalingPercentX

Scaling percentage in the horizontal (x) direction with respect to the normal paper size. Must be in the range of 1 to 1000. Set to 100 if scaling will not be done.

<div class="alert"><b>Note</b>    To ensure predictable printing results, <b>dwScalingPercentX</b> and <b>dwScalingPercentY</b> must have the same value.</div>
<div> </div>

### -field dwScalingPercentY

Scaling percentage in the vertical (y) direction with respect to the normal paper size. Must be in the range of 1 to 1000. Set to 100 if scaling will not be done.

<div class="alert"><b>Note</b>    To ensure predictable printing results, <b>dwScalingPercentX</b> and <b>dwScalingPercentY</b> must have the same value.</div>
<div> </div>

## -remarks



If the <b>dmPrintQuality</b> member of a print job's DEVMODEW structure is a negative value, such as DMRES_HIGH, and if monochrome color optimization is enabled, then switching between color and monochrome could result in different resolutions being used. This is because DMRES_HIGH might be assigned to different DPI values for color and monochrome rendering. (For Unidrv-supported devices, this assignment occurs in the printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/">GPD</a> file.) To ensure a consistent resolution throughout the print job, the driver can specify positive <b>dmPrintQuality</b> and <b>dmYResolution</b> values (representing a specific DPI resolution) to override the equivalent <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> values. 

The EMF print processor uses the flag specified for <b>dwColorOptimization</b> to determine whether to request GDI to perform monochrome color optimization. If monochrome color optimization is enabled, the print job can be switched between monochrome and color rendering as appropriate.

If you are creating a Unidrv rendering plug-in to generate color watermarks, note that when the <b>dwColorOptimization</b> member is set to COLOR_OPTIMIZATION, color watermarks are printed in black and white when they are printed on black-and-white documents. To ensure that color watermarks print correctly with color and black-and-white documents, disable color optimization. Color optimization also can be controlled by the Unidrv *<b>ChangeColorModeOnDoc?</b> color attribute (see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/color-attributes">Color Attributes</a>), and by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdiendpageemf">GdiEndPageEMF</a> function.

For a list of default values for ATTRIBUTE_INFO_4 members, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-getjobattributesex">GetJobAttributesEx</a>.

This structure is available in Windows Vista.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2">ATTRIBUTE_INFO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3">ATTRIBUTE_INFO_3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdiendpageemf">GdiEndPageEMF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-getjobattributesex">GetJobAttributesEx</a>
 

 

