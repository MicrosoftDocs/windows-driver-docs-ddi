---
UID: NS:winsplp._MONITORUI
title: _MONITORUI (winsplp.h)
description: The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls.
old-location: print\monitorui.htm
tech.root: print
ms.date: 03/29/2021
keywords: ["MONITORUI structure"]
ms.keywords: "*PMONITORUI, MONITORUI, MONITORUI structure [Print Devices], PMONITORUI, PMONITORUI structure pointer [Print Devices], _MONITORUI, print.monitorui, spoolfnc_bcf5298e-b0b6-41c1-9152-9a804234fba9.xml, winsplp/MONITORUI, winsplp/PMONITORUI"
req.header: winsplp.h
req.include-header: Winsplp.h
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
targetos: Windows
req.typenames: MONITORUI, *PMONITORUI
f1_keywords:
 - _MONITORUI
 - winsplp/_MONITORUI
 - PMONITORUI
 - winsplp/PMONITORUI
 - MONITORUI
 - winsplp/MONITORUI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - _MONITORUI
 - PMONITORUI
 - MONITORUI
---

# _MONITORUI structure

## -description

The **MONITORUI** structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls.

## -struct-fields

### -field dwMonitorUISize

Size, in bytes, of the **MONITORUI** structure.

### -field pfnAddPortUI

Pointer to the port monitor UI DLL [AddPortUI](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-addportui) function that adds a printer port, then obtains port configuration information from the user and sends it to the port monitor server DLL.

### -field pfnConfigurePortUI

Pointer to the port monitor UI DLL [ConfigurePortUI](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-configureportui) function that obtains port configuration information from the user and sends it to the port monitor server DLL.

### -field pfnDeletePortUI

Pointer to the port monitor UI DLL [DeletePortUI](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-deleteportui) function that deletes a printer port.

## -remarks

All structure members must be initialized by the port monitor UI DLL. The structure's address is passed to the print spooler as the return value for the [InitializePrintMonitorUI](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitorui) function.

## -see-also

[InitializePrintMonitorUI](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitorui)
