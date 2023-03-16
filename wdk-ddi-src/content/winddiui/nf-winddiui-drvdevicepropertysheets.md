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

Caller-supplied pointer to a [**PROPSHEETUI_INFO**](../compstui/ns-compstui-_propsheetui_info.md) structure.

### -param lParam

Caller-supplied integer value that is dependent on the contents of the **Reason** member of the PROPSHEETUI_INFO structure, as listed in the following table.

| Reason value | Definition of *lParam* |
|---|---|
| PROPSHEETUI_REASON_INIT | Pointer to a [**DEVICEPROPERTYHEADER**](./ns-winddiui-_devicepropertyheader.md) structure. |
| All other reason values | See the description of the *lParam* parameter for the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type. (The [**DEVICEPROPERTYHEADER**](./ns-winddiui-_devicepropertyheader.md) structure's address is contained in the **lParamInit** member of the [**PROPSHEETUI_INFO**](../compstui/ns-compstui-_propsheetui_info.md) structure.) |

## -returns

See the ReturnValue section in the description of the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type.

## -remarks

All [printer interface DLLs](/windows-hardware/drivers/print/printer-interface-dll) must provide a **DrvDevicePropertySheets** function, which is defined using the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type. The function's purpose is to call the [ComPropSheet](../compstui/nc-compstui-pfncompropsheet.md) function, provided by [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface), to specify a property sheet page containing user-modifiable properties for the printer.

The function should perform operations as described for the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type. The function should create the printer's DeviceSettings property sheet page (see the **pDlgPage** member of the [**COMPROPSHEETUI**](../compstui/ns-compstui-_compropsheetui.md) structure).

Printer device settings should be stored in the registry. If a user with administrator privilege modifies options on the DeviceSettings page, the **DrvDevicePropertySheets** function should write the updated values to the registry by calling SetPrinterData (described in the Microsoft Windows SDK documentation).

## -see-also

[DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md)

[IPrintOemUI::DevicePropertySheets](../prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets.md)