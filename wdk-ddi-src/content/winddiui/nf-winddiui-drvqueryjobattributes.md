---
UID: NF:winddiui.DrvQueryJobAttributes
title: DrvQueryJobAttributes function
author: windows-driver-content
description: The DrvQueryJobAttributes function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page (&#0034;N-up&#0034; printing), printing multiple copies of each page, collating pages, and printing pages in reverse order.
old-location: print\drvqueryjobattributes.htm
old-project: print
ms.assetid: 71e07572-bb15-4838-94d1-e07a3305ab82
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DrvQueryJobAttributes function [Print Devices], winddiui/DrvQueryJobAttributes, print.drvqueryjobattributes, print_interface-graphics_3fc2f9a4-bfe5-4323-a73e-6ac3ca9cf217.xml, DrvQueryJobAttributes
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
-	DrvQueryJobAttributes
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvQueryJobAttributes function


## -description


The <b>DrvQueryJobAttributes</b> function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page ("N-up" printing), printing multiple copies of each page, collating pages, and printing pages in reverse order.


## -syntax


````
BOOL DrvQueryJobAttributes(
  _In_  HANDLE   hPrinter,
  _In_  PDEVMODE pDevMode,
  _In_  DWORD    dwLevel,
  _Out_ LPBYTE   lpAttributeInfo
);
````


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

<a href="..\winddiui\ns-winddiui-_attribute_info_1.md">ATTRIBUTE_INFO_1</a>


</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="..\winddiui\ns-winddiui-_attribute_info_2.md">ATTRIBUTE_INFO_2</a>


</td>
</tr>
<tr>
<td>
3

</td>
<td>

<a href="..\winddiui\ns-winddiui-_attribute_info_3.md">ATTRIBUTE_INFO_3</a>


</td>
</tr>
<tr>
<td>
4

</td>
<td>

<a href="..\winddiui\ns-winddiui-_attribute_info_4.md">ATTRIBUTE_INFO_4</a>


</td>
</tr>
</table> 


### -param lpAttributeInfo [out]

Caller-supplied pointer to a structure identified by <i>dwLevel</i>.


## -returns


If the operation succeeds, the function should return <b>TRUE</b>. Otherwise, it should return <b>FALSE</b>. Returning <b>FALSE</b> causes the current print job to be canceled.



## -remarks


A <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> can optionally provide a <b>DrvQueryJobAttributes</b> function. If the function is provided, it should fill in the supplied structure, described by <i>dwLevel</i> and <i>plAttributeInfo</i>, to indicate the current print job's user-requested attributes (such as N-up parameters and the number of copies) and the driver's ability to support those attributes. The function is typically called by the EMF print processor, so it can determine which job attributes can be handled by the driver (or printer), and which must be handled by the print processor.

For descriptions of the job attributes that the function can specify, see the descriptions of <a href="..\winddiui\ns-winddiui-_attribute_info_1.md">ATTRIBUTE_INFO_1</a>, <a href="..\winddiui\ns-winddiui-_attribute_info_2.md">ATTRIBUTE_INFO_2</a>, <a href="..\winddiui\ns-winddiui-_attribute_info_3.md">ATTRIBUTE_INFO_3</a>, and <a href="..\winddiui\ns-winddiui-_attribute_info_4.md">ATTRIBUTE_INFO_4</a>.

The ATTRIBUTE_INFO_4 structure is defined for Windows Vista.



## -see-also

<a href="..\winddiui\ns-winddiui-_attribute_info_2.md">ATTRIBUTE_INFO_2</a>

<a href="..\winddiui\ns-winddiui-_attribute_info_4.md">ATTRIBUTE_INFO_4</a>

<a href="..\winddiui\ns-winddiui-_attribute_info_3.md">ATTRIBUTE_INFO_3</a>

<a href="..\winddiui\ns-winddiui-_attribute_info_1.md">ATTRIBUTE_INFO_1</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvQueryJobAttributes function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

