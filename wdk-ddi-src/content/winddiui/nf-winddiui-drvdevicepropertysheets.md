---
UID: NF:winddiui.DrvDevicePropertySheets
title: DrvDevicePropertySheets function (winddiui.h)
description: A printer interface DLL's DrvDevicePropertySheets function is responsible for creating property sheet pages that describe a printer's properties.
tech.root: print
ms.date: 03/09/2023
keywords: ["DrvDevicePropertySheets function"]
ms.keywords: DrvDevicePropertySheets, DrvDevicePropertySheets function [Print Devices], print.drvdevicepropertysheets, print_interface-graphics_f7a16b0a-c0f3-48c8-83a0-ce44a80ff546.xml, winddiui/DrvDevicePropertySheets
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DrvDevicePropertySheets
 - winddiui/DrvDevicePropertySheets
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvDevicePropertySheets
---

## -description

A printer interface DLL's **DrvDevicePropertySheets** function is responsible for creating property sheet pages that describe a printer's properties.

## -parameters

### -param pPSUIInfo [in, optional]

Caller-supplied pointer to a [**PROPSHEETUI_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure.

### -param lParam

Caller-supplied integer value that is dependent on the contents of the **Reason** member of the PROPSHEETUI_INFO structure, as listed in the following table.

| Reason value | Definition of *lParam* |
|---|---|
| PROPSHEETUI_REASON_INIT | Pointer to a [**DEVICEPROPERTYHEADER**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_devicepropertyheader) structure. |
| All other reason values | See the description of the *lParam* parameter for the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) function type. (The [**DEVICEPROPERTYHEADER**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_devicepropertyheader) structure's address is contained in the **lParamInit** member of the [**PROPSHEETUI_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure.) |

## -returns

See the ReturnValue section in the description of the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) function type.

## -remarks

All [printer interface DLLs](/windows-hardware/drivers/print/printer-interface-dll) must provide a **DrvDevicePropertySheets** function, which is defined using the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) function type. The function's purpose is to call the [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function, provided by [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface), to specify a property sheet page containing user-modifiable properties for the printer.

The function should perform operations as described for the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) function type. The function should create the printer's DeviceSettings property sheet page (see the **pDlgPage** member of the [**COMPROPSHEETUI**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui) structure).

Printer device settings should be stored in the registry. If a user with administrator privilege modifies options on the DeviceSettings page, the **DrvDevicePropertySheets** function should write the updated values to the registry by calling SetPrinterData (described in the Microsoft Windows SDK documentation).

## -see-also

[DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets)

[IPrintOemUI::DevicePropertySheets](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets)
