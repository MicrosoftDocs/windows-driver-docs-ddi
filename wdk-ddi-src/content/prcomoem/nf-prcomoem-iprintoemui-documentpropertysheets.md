---
UID: NF:prcomoem.IPrintOemUI.DocumentPropertySheets
title: IPrintOemUI::DocumentPropertySheets (prcomoem.h)
description: The IPrintOemUI::DocumentPropertySheets method allows a user interface plug-in to append a new page to a printer device's document property sheet.
old-location: print\iprintoemui_documentpropertysheets.htm
tech.root: print
ms.assetid: a8c7eb0d-792f-4a6c-af47-bb4558feb790
ms.date: 04/20/2018
keywords: ["IPrintOemUI::DocumentPropertySheets"]
ms.keywords: DocumentPropertySheets, DocumentPropertySheets method [Print Devices], DocumentPropertySheets method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],DocumentPropertySheets method, IPrintOemUI.DocumentPropertySheets, IPrintOemUI::DocumentPropertySheets, prcomoem/IPrintOemUI::DocumentPropertySheets, print.iprintoemui_documentpropertysheets, print_unidrv-pscript_ui_a998749c-eb3d-4b54-a69c-c7cdc61930fc.xml
req.header: prcomoem.h
req.include-header: Prcomoem.h, Compstui.h
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
 - IPrintOemUI::DocumentPropertySheets
 - prcomoem/IPrintOemUI::DocumentPropertySheets
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUI.DocumentPropertySheets
---

# IPrintOemUI::DocumentPropertySheets


## -description

The <code>IPrintOemUI::DocumentPropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's document property sheet.

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

The return value depends on the contents of the PROPSHEETUI_INFO structure's <b>Reason</b> member. For more information, see the description of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a>.

## -remarks

A user interface plug-in's <code>IPrintOemUI::DocumentPropertySheets</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function that is exported by user-mode printer interface DLLs. Both functions have the same input parameters.

If you provide a user interface plug-in, the <code>IPrintOemUI::DocumentPropertySheets</code> method is called after the driver's <b>DrvDocumentPropertySheets</b> function is called.

When <code>IPrintOemUI::DocumentPropertySheets</code> is called, the <b>lParamInit</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure contains the address of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuipsparam">OEMUIPSPARAM</a> structure.

If you implement this method, you typically also supply a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>-typed callback function to handle user modifications. This callback function must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting">IPrintOemDriverUI::DrvUpdateUISetting</a> to inform the driver when the value associated with a user interface setting has been modified, if the value is stored in the driver's <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure (instead of the plug-in's private DEVMODEW members ) or in registry keys.

If <code>IPrintOemUI::DocumentPropertySheets</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

If one user interface plug-in supports several printer models, and if you only want the new page to be displayed for some of those models, the <code>IPrintOemUI::DocumentPropertySheets</code> method should just provide a success return value, without actually adding the page, for the models not requiring the page.

For more information about creating and installing user interface plug-ins, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui">IPrintOemUI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>

