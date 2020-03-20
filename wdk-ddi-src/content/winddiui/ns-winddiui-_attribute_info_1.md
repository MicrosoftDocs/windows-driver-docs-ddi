---
UID: NS:winddiui._ATTRIBUTE_INFO_1
title: _ATTRIBUTE_INFO_1 (winddiui.h)
description: The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied.
old-location: print\attribute_info_1.htm
tech.root: print
ms.assetid: 7902877c-4991-48ae-9285-82949f898af2
ms.date: 04/20/2018
keywords: ["_ATTRIBUTE_INFO_1 structure"]
ms.keywords: "*PATTRIBUTE_INFO_1, ATTRIBUTE_INFO_1, ATTRIBUTE_INFO_1 structure [Print Devices], PATTRIBUTE_INFO_1, PATTRIBUTE_INFO_1 structure pointer [Print Devices], _ATTRIBUTE_INFO_1, print.attribute_info_1, print_interface-graphics_6c838297-1acb-4d8f-aa5d-beab06a6d3d2.xml, winddiui/ATTRIBUTE_INFO_1, winddiui/PATTRIBUTE_INFO_1"
f1_keywords:
 - "winddiui/ATTRIBUTE_INFO_1"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winddiui.h
api_name:
- ATTRIBUTE_INFO_1
product:
- Windows
targetos: Windows
req.typenames: ATTRIBUTE_INFO_1, *PATTRIBUTE_INFO_1
---

# _ATTRIBUTE_INFO_1 structure


## -description


The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> function. All member values are function-supplied.


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


## -remarks



The caller (the EMF print processor) uses the <b>dwJobNumberOfPagesPerSide</b> and <b>dwDrvNumberOfPagesPerSide</b> members to determine whether the driver or the print processor handles "N-up" printing.

If the print processor handles "N-up" printing, it checks <b>dwNupBorderFlags</b> to determine if it should draw a page border.

The print processor checks <b>dwJobPageOrderFlags</b> and <b>dwDrvPageOrderFlags</b> to determine the order in which pages should be sent to the printer.

The print processor uses <b>dwJobNumberOfCopies</b> and <b>dwDrvNumberOfCopies</b> to determine the number of times the print job must be sent to the printer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a>
 

 

