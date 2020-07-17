---
UID: NS:winddiui._DRIVER_UPGRADE_INFO_1
title: _DRIVER_UPGRADE_INFO_1 (winddiui.h)
description: The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function.
old-location: print\driver_upgrade_info_1.htm
tech.root: print
ms.assetid: fef7c63b-ca9e-47f4-96cb-4dafa080ddcf
ms.date: 04/20/2018
keywords: ["_DRIVER_UPGRADE_INFO_1 structure"]
ms.keywords: "*PDRIVER_UPGRADE_INFO_1, DRIVER_UPGRADE_INFO_1, DRIVER_UPGRADE_INFO_1 structure [Print Devices], PDRIVER_UPGRADE_INFO_1, PDRIVER_UPGRADE_INFO_1 structure pointer [Print Devices], _DRIVER_UPGRADE_INFO_1, print.driver_upgrade_info_1, print_interface-graphics_eb7333cb-f073-4c0b-ade4-20a477d28f67.xml, winddiui/DRIVER_UPGRADE_INFO_1, winddiui/PDRIVER_UPGRADE_INFO_1"
f1_keywords:
 - "winddiui/DRIVER_UPGRADE_INFO_1"
 - "DRIVER_UPGRADE_INFO_1"
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Windows
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
- HeaderDef
api_location:
- winddiui.h
api_name:
- DRIVER_UPGRADE_INFO_1
product:
- Windows
targetos: Windows
req.typenames: DRIVER_UPGRADE_INFO_1, *PDRIVER_UPGRADE_INFO_1
---

# _DRIVER_UPGRADE_INFO_1 structure


## -description


The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvupgradeprinter">DrvUpgradePrinter</a> function.


## -struct-fields




### -field pPrinterName

Pointer to a NULL-terminated string that specifies the name of the printer.


### -field pOldDriverDirectory

Pointer to a NULL-terminated string that specifies the local directory in which the old printer driver files can be found.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_driver_upgrade_info_2">DRIVER_UPGRADE_INFO_2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvupgradeprinter">DrvUpgradePrinter</a>
 

 

