---
UID: NF:winddiui.DrvQueryJobAttributes
title: DrvQueryJobAttributes function
author: windows-driver-content
description: The DrvQueryJobAttributes function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page (&#0034;N-up&#0034; printing), printing multiple copies of each page, collating pages, and printing pages in reverse order.
old-location: print\drvqueryjobattributes.htm
tech.root: print
ms.assetid: 71e07572-bb15-4838-94d1-e07a3305ab82
ms.date: 4/20/2018
ms.keywords: DrvQueryJobAttributes, DrvQueryJobAttributes function [Print Devices], print.drvqueryjobattributes, print_interface-graphics_3fc2f9a4-bfe5-4323-a73e-6ac3ca9cf217.xml, winddiui/DrvQueryJobAttributes
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
-	DrvQueryJobAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvQueryJobAttributes function


## -description


The <b>DrvQueryJobAttributes</b> function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page ("N-up" printing), printing multiple copies of each page, collating pages, and printing pages in reverse order.


## -parameters




### -param hPrinter [in]

Caller-supplied printer handle.


### -param pDevMode [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param dwLevel [in]

Caller-supplied value indicating the type of structure pointed to by <i>lpAttributeInfo</i>, as indicated in the following table.

<table>
<tr>
<th><i>dwLevel</i> Value</th>
<th>Structure pointed to by <i>lpAttributeInfo</i></th>
</tr>
<tr>
<td>
1

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>


</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545091">ATTRIBUTE_INFO_2</a>


</td>
</tr>
<tr>
<td>
3

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a>


</td>
</tr>
<tr>
<td>
4

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>


</td>
</tr>
</table>
 


### -param lpAttributeInfo [out]

Caller-supplied pointer to a structure identified by <i>dwLevel</i>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise, it should return <b>FALSE</b>. Returning <b>FALSE</b> causes the current print job to be canceled.




## -remarks



A <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> can optionally provide a <b>DrvQueryJobAttributes</b> function. If the function is provided, it should fill in the supplied structure, described by <i>dwLevel</i> and <i>plAttributeInfo</i>, to indicate the current print job's user-requested attributes (such as N-up parameters and the number of copies) and the driver's ability to support those attributes. The function is typically called by the EMF print processor, so it can determine which job attributes can be handled by the driver (or printer), and which must be handled by the print processor.

For descriptions of the job attributes that the function can specify, see the descriptions of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545091">ATTRIBUTE_INFO_2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>.

The ATTRIBUTE_INFO_4 structure is defined for Windows Vista.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545091">ATTRIBUTE_INFO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>
 

 

