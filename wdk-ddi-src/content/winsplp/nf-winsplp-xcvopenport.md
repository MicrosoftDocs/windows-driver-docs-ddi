---
UID: NF:winsplp.XcvOpenPort
title: XcvOpenPort function (winsplp.h)
description: A port monitor server DLL's XcvOpenPort function opens a port for configuration operations.
tech.root: print
ms.date: 07/27/2022
keywords: ["XcvOpenPort function"]
ms.keywords: print.xcvopenport, spoolfnc_d2e14d20-1b34-49f5-a627-7b08ccc79ccf.xml, winsplp/XcvOpenPort, XcvOpenPort function [Print Devices], XcvOpenPort
req.header: winsplp.h
req.include-header: Winsplp.h
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
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
f1_keywords:
 - XcvOpenPort
 - winsplp/XcvOpenPort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - XcvOpenPort
---

## -description

A port monitor server DLL's **XcvOpenPort** function opens a port for configuration operations.

## -parameters

### -param pszObject

Caller-supplied pointer to a string representing the name of the port. Can be **NULL**, and most monitors do not need this parameter.

### -param GrantedAccess

Caller-supplied ACCESS_MASK structure containing the access granted to the user during a print monitor UI DLL's call to the spooler's **OpenPrinter** function. See the following Remarks section.

### -param phXcv

Caller-supplied pointer to a location to receive a function-supplied port handle.

## -returns

If the operation succeeds, the function should return **TRUE**. Otherwise it should return **FALSE**.

## -remarks

Port monitor server DLLs are required to define an **XcvOpenPort** function and include its address in a [MONITOR2](..\winsplp\ns-winsplp-_monitor2.md) structure.

The spooler's **OpenPrinter** function (described in the Microsoft Windows SDK documentation) calls **XcvOpenPort** if the specified printer name includes either of the strings "XcvPort" or "XcvMonitor". For more information, see [AddPortUI](..\winsplp\nf-winsplp-addportui.md).

The **XcvOpenPort** function should open the port for configuration purposes. This operation might only consist of storing the input arguments for subsequent use within [XcvDataPort](..\winsplp\nf-winsplp-xcvdataport.md). The function should return a handle to the stored information in the location pointed to by *phXcv*. This handle is returned to the caller of **OpenPrinter**, and subsequently received as an input argument to **XcvDataPort**.

The function should save the granted access mask. Later, when the server DLL's **XcvDataPort** function is called, the granted access should be compared with SERVER_ACCESS_ADMINISTER and if the comparison fails, **XcvDataPort** should return ERROR_ACCESS_DENIED.

## -see-also

[InitializePrintMonitor2](..\winsplp\nf-winsplp-initializeprintmonitor2.md)

[XcvClosePort](..\winsplp\nf-winsplp-xcvcloseport.md)

[XcvDataPort](..\winsplp\nf-winsplp-xcvdataport.md)

[AddPortUI](..\winsplp\nf-winsplp-addportui.md)
