---
UID: NF:prcomoem.IPrintOemUI2.QueryJobAttributes
title: IPrintOemUI2::QueryJobAttributes method
author: windows-driver-content
description: The IPrintOemUI2::QueryJobAttributes method allows a UI plug-in to postprocess the core driver's results after a call to the DrvQueryJobAttributes DDI.
old-location: print\iprintoemui2_queryjobattributes.htm
old-project: print
ms.assetid: cb510aa6-7156-4b02-bab1-6951becbc1a0
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintoemui2_queryjobattributes, IPrintOemUI2, print_unidrv-pscript_ui_5c5f2adc-9410-428b-89b5-39925c7fb8f9.xml, prcomoem/IPrintOemUI2::QueryJobAttributes, IPrintOemUI2::QueryJobAttributes, QueryJobAttributes method [Print Devices], IPrintOemUI2 interface, QueryJobAttributes method [Print Devices], QueryJobAttributes, IPrintOemUI2 interface [Print Devices], QueryJobAttributes method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemUI2.QueryJobAttributes
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintOemUI2::QueryJobAttributes method


## -description


The <code>IPrintOemUI2::QueryJobAttributes</code> method allows a UI plug-in to postprocess the core driver's results after a call to the <a href="..\winddiui\nf-winddiui-drvqueryjobattributes.md">DrvQueryJobAttributes</a> DDI. The plug-in can choose to overwrite the values that the core driver placed in the <i>lpAttributeInfo</i> output buffer.


## -syntax


````
HRESULT QueryJobAttributes(
   HANDLE   hPrinter,
   PDEVMODE pDevmode,
   DWORD    dwLevel,
   LPBYTE   lpAttributeInfo
);
````


## -parameters




### -param hPrinter

Specifies the caller-supplied printer handle.


### -param pDevmode

Pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param dwLevel

Specifies a caller-supplied value indicating the type of structure pointed to by <i>lpAttributeInfo</i>, as indicated in the following table.
<table>
<tr>
<th>Value</th>
<th>Structure Pointed to by <i>lpAttributeInfo</i></th>
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

Note that if this method changes any dwDrv<i>Xxx</i> member of the ATTRIBUTE_INFO_<i>N</i> structures, the spooler assumes that the plug-in is able to support the behavior represented by that member.


### -param lpAttributeInfo

Pointer to a memory location that receives the address of a structure of the type identified by <i>dwLevel</i>.


## -returns


If the UI plug-in supports this method, and the method succeeded, it should return S_OK. This causes the core driver to return <b>TRUE</b> for the <a href="..\winddiui\nf-winddiui-drvqueryjobattributes.md">DrvQueryJobAttributes</a> DDI. If the UI plug-in supports this method, but the method failed, it should return E_FAIL. This causes the core driver to return <b>FALSE</b> for the DrvQueryJobAttributes DDI. If the UI plug-in does not support this method, it should return E_NOTIMPL.



## -remarks


When the printer has multiple UI plug-ins installed, the core driver calls the UI plug-ins in the order they were installed. The HRESULT returned by the last UI plug-in that supports this method is used to determine the core driver's DrvQueryJobAttributes DDI return value as described in the previous section.

See <a href="..\winddiui\nf-winddiui-drvqueryjobattributes.md">DrvQueryJobAttributes</a> for more information.



## -see-also

<a href="..\winddiui\ns-winddiui-_attribute_info_2.md">ATTRIBUTE_INFO_2</a>

<a href="..\winddiui\ns-winddiui-_attribute_info_3.md">ATTRIBUTE_INFO_3</a>

<a href="..\winddiui\ns-winddiui-_attribute_info_1.md">ATTRIBUTE_INFO_1</a>

<a href="..\winddiui\nf-winddiui-drvqueryjobattributes.md">DrvQueryJobAttributes</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>

<a href="..\winddiui\ns-winddiui-_attribute_info_4.md">ATTRIBUTE_INFO_4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI2::QueryJobAttributes method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

