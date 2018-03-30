---
UID: NS:winddiui._ATTRIBUTE_INFO_2
title: "_ATTRIBUTE_INFO_2"
author: windows-driver-content
description: The ATTRIBUTE_INFO_2 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied.
old-location: print\attribute_info_2.htm
old-project: print
ms.assetid: c5bb9943-ee5b-4128-9e5f-438971119e3a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PATTRIBUTE_INFO_2, ATTRIBUTE_INFO_2, ATTRIBUTE_INFO_2 structure [Print Devices], PATTRIBUTE_INFO_2, PATTRIBUTE_INFO_2 structure pointer [Print Devices], _ATTRIBUTE_INFO_2, print.attribute_info_2, print_interface-graphics_681158ae-a9ad-40f6-a3de-c82cda7156e0.xml, winddiui/ATTRIBUTE_INFO_2, winddiui/PATTRIBUTE_INFO_2"
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
-	ATTRIBUTE_INFO_2
product: Windows
targetos: Windows
req.typenames: ATTRIBUTE_INFO_2, *PATTRIBUTE_INFO_2
req.product: Windows 10 or later.
---

# _ATTRIBUTE_INFO_2 structure


## -description


The ATTRIBUTE_INFO_2 structure is used as a parameter for a printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548581">DrvQueryJobAttributes</a> function. All member values are function-supplied.


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
 


## -remarks



The EMF print processor uses the flag specified for <b>dwColorOptimization</b> to determine whether to request GDI to perform monochrome color optimization. If monochrome color optimization is enabled, the print job can be switched between monochrome and color rendering as appropriate.

If you are creating a Unidrv rendering plug-in to generate color watermarks, note that when the <b>dwColorOptimization</b> member is set to COLOR_OPTIMIZATION, color watermarks are printed in black and white when they are printed on black-and-white documents. To ensure that color watermarks print correctly with color and black-and-white documents, disable color optimization. Color optimization also can be controlled by the Unidrv *<b>ChangeColorModeOnDoc?</b> color attribute (see <a href="https://msdn.microsoft.com/c8de0186-9cf5-43e5-81e7-33351a34c13c">Color Attributes</a>), and by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549468">GdiEndPageEMF</a> function. 

For more information about other structure members, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548581">DrvQueryJobAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549468">GdiEndPageEMF</a>
 

 

