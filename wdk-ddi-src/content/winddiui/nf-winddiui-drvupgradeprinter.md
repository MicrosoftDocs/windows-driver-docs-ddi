---
UID: NF:winddiui.DrvUpgradePrinter
title: DrvUpgradePrinter function (winddiui.h)
description: A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system.
tech.root: print
ms.date: 03/09/2023
keywords: ["DrvUpgradePrinter function"]
ms.keywords: DrvUpgradePrinter, DrvUpgradePrinter function [Print Devices], print.drvupgradeprinter, print_interface-graphics_ab060948-18bc-4b0f-a504-320083fcb173.xml, winddiui/DrvUpgradePrinter
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
 - DrvUpgradePrinter
 - winddiui/DrvUpgradePrinter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvUpgradePrinter
---

## -description

A printer interface DLL's **DrvUpgradePrinter** function is used for updating a printer's registry settings when a new version of the driver is added to a system.

## -parameters

### -param Level

Caller-supplied value indicating the type of structure pointed to by *pDriverUpgradeInfo*, as indicated in the following table.

| *Level* value | Structure pointed to by *pDriverUpgradeInfo* |
|---|---|
| 1 | [**DRIVER_UPGRADE_INFO_1**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_driver_upgrade_info_1) |
| 2 | [**DRIVER_UPGRADE_INFO_2**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_driver_upgrade_info_2) |

### -param pDriverUpgradeInfo [in, optional]

Caller-supplied pointer to a structure whose type is identified by *dwLevel*.

## -returns

If the operation succeeds, the function should return **TRUE**; otherwise, it should call SetLastError to set an error code and return **FALSE**.

## -remarks

A [printer interface DLL](/windows-hardware/drivers/print/printer-interface-dll) can optionally provide a **DrvUpgradePrinter** function. If it does, the spooler calls it for every printer when the printer driver is copied onto the system. This occurs when a system is upgraded from one operating system release to the next, or when an application updates a printer driver by calling the Win32 **AddPrinterDriver** function.

Often, a new driver version requires registry settings that are different from those of the old version. The **DrvUpgradePrinter** function's purpose is to update the registry so it is compatible with the driver. For more information about storing printer information in the registry, see [DrvPrinterEvent](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvprinterevent).

For Windows 2000 and later, when the spooler calls **DrvUpgradePrinter**, it supplies a DRIVER_UPGRADE_INFO_2 structure pointer for *pDriverUpgradeInfo*. If the function returns **FALSE**, the spooler calls the function again, this time specifying a DRIVER_UPGRADE_INFO_1 structure pointer. If this call returns **FALSE**, the spooler writes an entry in the event log.

For Windows NT 4.0 and previous, when the spooler calls **DrvUpgradePrinter**, it supplies a DRIVER_UPGRADE_INFO_1 structure pointer for *pDriverUpgradeInfo*. If the function returns **FALSE**, the spooler writes an entry in the event log.

## -see-also

[**DRIVER_UPGRADE_INFO_1**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_driver_upgrade_info_1)

[**DRIVER_UPGRADE_INFO_2**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_driver_upgrade_info_2)

[DrvPrinterEvent](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvprinterevent)
