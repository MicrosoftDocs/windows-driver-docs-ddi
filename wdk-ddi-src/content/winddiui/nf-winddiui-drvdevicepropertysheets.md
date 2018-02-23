---
UID: NF:winddiui.DrvDevicePropertySheets
title: DrvDevicePropertySheets function
author: windows-driver-content
description: A printer interface DLL's DrvDevicePropertySheets function is responsible for creating property sheet pages that describe a printer's properties.
old-location: print\drvdevicepropertysheets.htm
old-project: print
ms.assetid: 46f39e36-8915-4ccf-97ef-45dbacdfbe0a
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: winddiui/DrvDevicePropertySheets, print_interface-graphics_f7a16b0a-c0f3-48c8-83a0-ce44a80ff546.xml, DrvDevicePropertySheets, print.drvdevicepropertysheets, DrvDevicePropertySheets function [Print Devices]
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
-	DrvDevicePropertySheets
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvDevicePropertySheets function


## -description


A printer interface DLL's <b>DrvDevicePropertySheets</b> function is responsible for creating property sheet pages that describe a printer's properties.


## -syntax


````
LONG DrvDevicePropertySheets(
  _In_opt_ PPROPSHEETUI_INFO pPSUIInfo,
           LPARAM            lParam
);
````


## -parameters




### -param pPSUIInfo [in, optional]

Caller-supplied pointer to a <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.


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
Pointer to a <a href="..\winddiui\ns-winddiui-_devicepropertyheader.md">DEVICEPROPERTYHEADER</a> structure.

</td>
</tr>
<tr>
<td>
All other reason values

</td>
<td>
See the description of the <i>lParam</i> parameter for the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type.

(The <a href="..\winddiui\ns-winddiui-_devicepropertyheader.md">DEVICEPROPERTYHEADER</a> structure's address is contained in the <b>lParamInit</b> member of the <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.)

</td>
</tr>
</table>
 


## -returns



See the ReturnValue section in the description of the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type.




## -remarks



All <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLLs</a> must provide a <b>DrvDevicePropertySheets</b> function, which is defined using the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type. The function's purpose is to call the <a href="..\compstui\nc-compstui-pfncompropsheet.md">ComPropSheet</a> function, provided by <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a>, to specify a property sheet page containing user-modifiable properties for the printer.

The function should perform operations as described for the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type. The function should create the printer's DeviceSettings property sheet page (see the <b>pDlgPage</b> member of the <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure).

Printer device settings should be stored in the registry. If a user with administrator privilege modifies options on the DeviceSettings page, the <b>DrvDevicePropertySheets</b> function should write the updated values to the registry by calling SetPrinterData (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>



<a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvDevicePropertySheets function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

