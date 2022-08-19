---
UID: NF:winsplp.AddPortUI
title: AddPortUI function (winsplp.h)
description: A port monitor UI DLL's AddPortUI function adds a printer port, then obtains port configuration information from the user and sends it to the port monitor server DLL.
tech.root: print
ms.date: 07/27/2022
keywords: ["AddPortUI function"]
ms.keywords: AddPortUI, pfnAddPortUI, pfnAddPortUI function [Print Devices], print.addportui, spoolfnc_e82f0e4d-e4f2-44b8-b957-3fc1b35e8a34.xml, winsplp/pfnAddPortUI
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AddPortUI
 - winsplp/AddPortUI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - AddPortUI
---

## -description

A port monitor UI DLL's **AddPortUI** function adds a printer port, then obtains port configuration information from the user and sends it to the port monitor server DLL.

## -parameters

### -param pszServer [in, optional]

Caller-supplied pointer to a string representing a server name, or **NULL** if the printer is local.

### -param hWnd [in]

Caller-supplied handle of the window that should be used as the parent for dialog boxes. If **NULL**, no dialog boxes should be displayed.

### -param pszMonitorNameIn

Caller-supplied pointer to a string representing the name of the monitor. Can be **NULL**.

### -param ppszPortNameOut [out, optional]

Caller-supplied pointer to a location to receive a port name string. Can be **NULL**, in which case a name is not returned.

## -returns

If the operation succeeds, the function should return **TRUE**. Otherwise SetLastError should be called to specify an error code, and the function should return **FALSE**. If the operation is canceled by the user or is unsupported, the function should call SetLastError(ERROR_CANCELLED), then return **FALSE**.

## -remarks

Port monitor UI DLLs are required to define an **AddPortUI** function and include the function's address in a [MONITORUI](./ns-winsplp-_monitorui.md) structure.

The spooler calls **AddPortUI** from within its AddPort function. The first three arguments received by **AddPortUI** are the arguments received by AddPort. (The AddPort function is described in the Microsoft Windows SDK documentation.)

The function should perform the following operations:

1. Call OpenPrinter, specifying a printer name with the following format:

    \\\\*ServerName*\\,XcvMonitor*MonitorName*

    where *ServerName* and *MonitorName* are the server and monitor names received as **AddPortUI** function arguments.

    The call to OpenPrinter requires a PRINTER_DEFAULTS structure, which is described in the Windows SDK documentation. The structure's **DesiredAccess** member must be set to SERVER_ACCESS_ADMINISTER. Its **pDatatype** and **pDevMode** members can be **NULL**.

    This call causes the print monitor server DLL's [XcvOpenPort](./nf-winsplp-xcvopenport.md) function to be called.

1. Obtain a port name from the user by displaying a dialog box.

1. Call [XcvData](/previous-versions/ff564255(v=vs.85)), specifying the following input arguments:

    - The handle received from OpenPrinter

    - The port name received from the user

    - A customized data name string, such as "PortExists"

    This call causes the server DLL's [XcvDataPort](./nf-winsplp-xcvdataport.md) function to be called. The **XcvDataPort** function should return a value that indicates whether the specified port name has already been used. If it has, the UI DLL should request another name from the user and call [XcvData](/previous-versions/ff564255(v=vs.85)) again.

1. After a valid new port name has been received, call [XcvData](/previous-versions/ff564255(v=vs.85)) again, this time specifying the following input arguments

    - The handle received from OpenPrinter

    - The validated port name received from the user

    - A data name string of "AddPort"

    This call causes the server DLL's [XcvDataPort](./nf-winsplp-xcvdataport.md) function to be called again.

1. Obtain port configuration parameters from the user by displaying a dialog box.

1. Call [XcvData](/previous-versions/ff564255(v=vs.85)) one or more times, specifying customized data name strings, to send each configuration parameter to the server DLL. Each **XcvData** call causes the server's [XcvDataPort](./nf-winsplp-xcvdataport.md) function to be called.

1. Call ClosePrinter, specifying the handle received from OpenPrinter. This causes the server DLL's [XcvClosePort](./nf-winsplp-xcvcloseport.md) function to be called.

## -see-also

[MONITORUI](./ns-winsplp-_monitorui.md)

[XcvClosePort](./nf-winsplp-xcvcloseport.md)

[XcvData](/previous-versions/ff564255(v=vs.85))

[XcvDataPort](./nf-winsplp-xcvdataport.md)

[XcvOpenPort](./nf-winsplp-xcvopenport.md)