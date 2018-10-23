---
UID: NF:winddiui.DrvDevicePropertySheets
title: DrvDevicePropertySheets function
author: windows-driver-content
description: A printer interface DLL's DrvDevicePropertySheets function is responsible for creating property sheet pages that describe a printer's properties.
old-location: print\drvdevicepropertysheets.htm
tech.root: print
ms.assetid: 46f39e36-8915-4ccf-97ef-45dbacdfbe0a
ms.date: 04/20/2018
ms.keywords: DrvDevicePropertySheets, DrvDevicePropertySheets function [Print Devices], print.drvdevicepropertysheets, print_interface-graphics_f7a16b0a-c0f3-48c8-83a0-ce44a80ff546.xml, winddiui/DrvDevicePropertySheets
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
-	DrvDevicePropertySheets
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvDevicePropertySheets function


## -description


A printer interface DLL's <b>DrvDevicePropertySheets</b> function is responsible for creating property sheet pages that describe a printer's properties.


## -parameters




### -param pPSUIInfo [in, optional]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561767">PROPSHEETUI_INFO</a> structure.


### -param lParam

Caller-supplied integer value that is dependent on the contents of the <b>Reason</b> member of the PROPSHEETUI_INFO structure, as listed in the following table.

<table>
<tr>
<th>Reason value</th>
<th>Definition of <i>lParam</i></th>
</tr>
<tr>
<td>
PROPSHEETUI_REASON_INIT

</td>
<td>
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547524">DEVICEPROPERTYHEADER</a> structure.

</td>
</tr>
<tr>
<td>
All other reason values

</td>
<td>
See the description of the <i>lParam</i> parameter for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559812">PFNPROPSHEETUI</a> function type.

(The <a href="https://msdn.microsoft.com/library/windows/hardware/ff547524">DEVICEPROPERTYHEADER</a> structure's address is contained in the <b>lParamInit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561767">PROPSHEETUI_INFO</a> structure.)

</td>
</tr>
</table>
 


## -returns



See the ReturnValue section in the description of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559812">PFNPROPSHEETUI</a> function type.




## -remarks



All <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLLs</a> must provide a <b>DrvDevicePropertySheets</b> function, which is defined using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559812">PFNPROPSHEETUI</a> function type. The function's purpose is to call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function, provided by <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a>, to specify a property sheet page containing user-modifiable properties for the printer.

The function should perform operations as described for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559812">PFNPROPSHEETUI</a> function type. The function should create the printer's DeviceSettings property sheet page (see the <b>pDlgPage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure).

Printer device settings should be stored in the registry. If a user with administrator privilege modifies options on the DeviceSettings page, the <b>DrvDevicePropertySheets</b> function should write the updated values to the registry by calling SetPrinterData (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>
 

 

