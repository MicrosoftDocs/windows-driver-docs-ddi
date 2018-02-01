---
UID: NF:prcomoem.IPrintOemUI.DocumentPropertySheets
title: IPrintOemUI::DocumentPropertySheets method
author: windows-driver-content
description: The IPrintOemUI::DocumentPropertySheets method allows a user interface plug-in to append a new page to a printer device's document property sheet.
old-location: print\iprintoemui_documentpropertysheets.htm
old-project: print
ms.assetid: a8c7eb0d-792f-4a6c-af47-bb4558feb790
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DocumentPropertySheets method [Print Devices], DocumentPropertySheets method [Print Devices], IPrintOemUI interface, print.iprintoemui_documentpropertysheets, IPrintOemUI::DocumentPropertySheets, DocumentPropertySheets, IPrintOemUI, IPrintOemUI interface [Print Devices], DocumentPropertySheets method, prcomoem/IPrintOemUI::DocumentPropertySheets, print_unidrv-pscript_ui_a998749c-eb3d-4b54-a69c-c7cdc61930fc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	IPrintOemUI.DocumentPropertySheets
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::DocumentPropertySheets method


## -description


The <code>IPrintOemUI::DocumentPropertySheets</code> method allows a user interface plug-in to append a new page to a printer device's document property sheet.


## -syntax


````
HRESULT DocumentPropertySheets(
   PPROPSHEETUI_INFO pPSUIInfo,
   LPARAM            lParam
);
````


## -parameters




### -param pPSUIInfo

Caller-supplied pointer to a <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.


### -param lParam

Caller-supplied value that depends on the reason value in <i>pPSUIInfo</i>--&gt;<b>Reason</b>. The reason value can be one of the following constants, which are defined in compstui.h. For more information about these constants, see the Remarks section and <i>lParam</i> parameter description in the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type.

PROPSHEETUI_REASON_DESTROY

PROPSHEETUI_REASON_GET_ICON

PROPSHEETUI_REASON_GET_INFO_HEADER

PROPSHEETUI_REASON_INIT

PROPSHEETUI_REASON_SET_RESULT


## -returns


The return value depends on the contents of the PROPSHEETUI_INFO structure's <b>Reason</b> member. For more information, see the description of <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>.



## -remarks


A user interface plug-in's <code>IPrintOemUI::DocumentPropertySheets</code> method performs the same types of operations as the <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a> function that is exported by user-mode printer interface DLLs. Both functions have the same input parameters.

If you provide a user interface plug-in, the <code>IPrintOemUI::DocumentPropertySheets</code> method is called after the driver's <b>DrvDocumentPropertySheets</b> function is called.

When <code>IPrintOemUI::DocumentPropertySheets</code> is called, the <b>lParamInit</b> member of the <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure contains the address of an <a href="..\printoem\ns-printoem-_oemuipsparam.md">OEMUIPSPARAM</a> structure.

If you implement this method, you typically also supply a <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback function to handle user modifications. This callback function must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a> to inform the driver when the value associated with a user interface setting has been modified, if the value is stored in the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure (instead of the plug-in's private DEVMODEW members ) or in registry keys.

If <code>IPrintOemUI::DocumentPropertySheets</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

If one user interface plug-in supports several printer models, and if you only want the new page to be displayed for some of those models, the <code>IPrintOemUI::DocumentPropertySheets</code> method should just provide a success return value, without actually adding the page, for the models not requiring the page.

For more information about creating and installing user interface plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.



## -see-also

<a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>

<a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI::DocumentPropertySheets method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

