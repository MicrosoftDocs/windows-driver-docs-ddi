---
UID: NF:prcomoem.IPrintOemUI2.QueryJobAttributes
title: IPrintOemUI2::QueryJobAttributes (prcomoem.h)
description: The IPrintOemUI2::QueryJobAttributes method allows a UI plug-in to postprocess the core driver's results after a call to the DrvQueryJobAttributes DDI.
old-location: print\iprintoemui2_queryjobattributes.htm
tech.root: print
ms.assetid: cb510aa6-7156-4b02-bab1-6951becbc1a0
ms.date: 04/20/2018
keywords: ["IPrintOemUI2::QueryJobAttributes"]
ms.keywords: IPrintOemUI2 interface [Print Devices],QueryJobAttributes method, IPrintOemUI2.QueryJobAttributes, IPrintOemUI2::QueryJobAttributes, QueryJobAttributes, QueryJobAttributes method [Print Devices], QueryJobAttributes method [Print Devices],IPrintOemUI2 interface, prcomoem/IPrintOemUI2::QueryJobAttributes, print.iprintoemui2_queryjobattributes, print_unidrv-pscript_ui_5c5f2adc-9410-428b-89b5-39925c7fb8f9.xml
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemUI2::QueryJobAttributes
 - prcomoem/IPrintOemUI2::QueryJobAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUI2.QueryJobAttributes
---

# IPrintOemUI2::QueryJobAttributes


## -description

The <code>IPrintOemUI2::QueryJobAttributes</code> method allows a UI plug-in to postprocess the core driver's results after a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> DDI. The plug-in can choose to overwrite the values that the core driver placed in the <i>lpAttributeInfo</i> output buffer.

## -parameters

### -param hPrinter

Specifies the caller-supplied printer handle.

### -param pDevmode

Pointer to a caller-supplied <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_1">ATTRIBUTE_INFO_1</a>


</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2">ATTRIBUTE_INFO_2</a>


</td>
</tr>
<tr>
<td>
3

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3">ATTRIBUTE_INFO_3</a>


</td>
</tr>
<tr>
<td>
4

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4">ATTRIBUTE_INFO_4</a>


</td>
</tr>
</table>
 

Note that if this method changes any dwDrv<i>Xxx</i> member of the ATTRIBUTE_INFO_<i>N</i> structures, the spooler assumes that the plug-in is able to support the behavior represented by that member.

### -param lpAttributeInfo

Pointer to a memory location that receives the address of a structure of the type identified by <i>dwLevel</i>.

## -returns

If the UI plug-in supports this method, and the method succeeded, it should return S_OK. This causes the core driver to return <b>TRUE</b> for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> DDI. If the UI plug-in supports this method, but the method failed, it should return E_FAIL. This causes the core driver to return <b>FALSE</b> for the DrvQueryJobAttributes DDI. If the UI plug-in does not support this method, it should return E_NOTIMPL.

## -remarks

When the printer has multiple UI plug-ins installed, the core driver calls the UI plug-ins in the order they were installed. The HRESULT returned by the last UI plug-in that supports this method is used to determine the core driver's DrvQueryJobAttributes DDI return value as described in the previous section.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a> for more information.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_1">ATTRIBUTE_INFO_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2">ATTRIBUTE_INFO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3">ATTRIBUTE_INFO_3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4">ATTRIBUTE_INFO_4</a>



<a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvqueryjobattributes">DrvQueryJobAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui2">IPrintOemUI2</a>

