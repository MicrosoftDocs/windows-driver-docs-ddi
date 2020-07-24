---
UID: NF:prcomoem.IPrintOemUI.DevicePropertySheets
title: IPrintOemUI::DevicePropertySheets (prcomoem.h)
description: The IPrintOemUI::DevicePropertySheets method allows a user interface plug-in to append a new page to a printer device's printer property sheet.
old-location: print\iprintoemui_devicepropertysheets.htm
tech.root: print
ms.assetid: 7d782f53-2409-416d-a3be-dad932c440a1
ms.date: 04/20/2018
keywords: ["IPrintOemUI::DevicePropertySheets"]
ms.keywords: DevicePropertySheets, DevicePropertySheets method [Print Devices], DevicePropertySheets method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],DevicePropertySheets method, IPrintOemUI.DevicePropertySheets, IPrintOemUI::DevicePropertySheets, prcomoem/IPrintOemUI::DevicePropertySheets, print.iprintoemui_devicepropertysheets, print_unidrv-pscript_ui_3e31410b-e0b6-490f-aea1-62f3d99ba96d.xml
f1_keywords:
 - "prcomoem/IPrintOemUI.DevicePropertySheets"
 - "IPrintOemUI.DevicePropertySheets"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUI.DevicePropertySheets
targetos: Windows
req.typenames: 
---

# IPrintOemUI::DevicePropertySheets


## -description


The <code>IPrintOemUI::DevicePropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's printer property sheet.


## -parameters




### -param pPSUIInfo

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure.


### -param lParam

Caller-supplied value that depends on the reason value in <i>pPSUIInfo</i>--><b>Reason</b>. The reason value can be one of the following constants, which are defined in compstui.h. For more information about these constants, see the Remarks section and <i>lParam</i> parameter description in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> function type.

PROPSHEETUI_REASON_DESTROY

PROPSHEETUI_REASON_GET_ICON

PROPSHEETUI_REASON_GET_INFO_HEADER

PROPSHEETUI_REASON_INIT

PROPSHEETUI_REASON_SET_RESULT


## -returns



The return value depends on the contents of PROPSHEETUI_INFO structure's <b>Reason</b> member. For more information, see the description of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a>.




## -remarks



A user interface plug-in's <code>IPrintOemUI::DevicePropertySheets</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a> function that is exported by user-mode printer interface DLLs. Both functions have the same input parameters.

If you provide a user interface plug-in, the <code>IPrintOemUI::DevicePropertySheets</code> method is called after the driver's <b>DrvDevicePropertySheets</b> function is called.

When <code>IPrintOemUI::DevicePropertySheets</code> is called, the <b>lParamInit</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure contains the address of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuipsparam">OEMUIPSPARAM</a> structure.

If you implement this method, you typically also supply a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>-typed callback function to handle user modifications. This callback function must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting">IPrintOemDriverUI::DrvUpdateUISetting</a> to inform the driver when the value associated with a user interface setting has been modified, if the value is stored in the driver's <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure (instead of the plug-in's private DEVMODEW members) or in registry keys.

If <code>IPrintOemUI::DevicePropertySheets</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

If one user interface plug-in supports several printer models, and if you only want the new page to be displayed for some of those models, the <code>IPrintOemUI::DevicePropertySheets</code> method should just provide a success return value, without actually adding the page, for the models not requiring the page.

For more information about creating and installing user interface plug-ins, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui">IPrintOemUI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>
 

 

