---
UID: NF:winsplp.OpenPort
title: OpenPort function (winsplp.h)
description: A port monitor's OpenPort function opens a printer port.
tech.root: print
ms.date: 07/27/2022
keywords: ["OpenPort function"]
ms.keywords: spoolfnc_94948c6d-fab4-44ce-9650-72464d5e3fdf.xml, pfnOpenPort, print.openport, OpenPort, pfnOpenPort function [Print Devices], winsplp/pfnOpenPort
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
f1_keywords:
 - OpenPort
 - winsplp/OpenPort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - OpenPort
---

## -description

A port monitor's **OpenPort** function opens a printer port.

## -parameters

### -param pName

Caller-supplied pointer to a string containing the name of the port to be opened.

### -param pHandle

Caller-supplied pointer to a location to receive a port handle.

## -returns

If the operation succeeds, the function should return **TRUE**. Otherwise it should return **FALSE**.

## -remarks

Port monitor server DLLs are required to define an **OpenPort** function and include the function's address in a [MONITOR2](..\winsplp\ns-winsplp-_monitor2.md) structure.

The **OpenPort** function is called, either by a language monitor or by the print spooler, when a print queue is being connected to a port. The **OpenPort** function's primary purpose is to return a port handle that the caller can use as an input argument for subsequent calls to the port monitor's [StartDocPort](/previous-versions/ff562710(v=vs.85)), [WritePort](..\winsplp\nf-winsplp-writeport.md), [ReadPort](..\winsplp\nf-winsplp-readport.md), [EndDocPort](/previous-versions/ff548742(v=vs.85)), and [GetPrinterDataFromPort](/previous-versions/ff550506(v=vs.85)) functions.

Besides returning a port handle, the **OpenPort** function can perform initialization operations that need to be taken care of before read or write operations are performed. For example, if the port supports modifiable time-out values, the **OpenPort** function should set these values.

Calls to **OpenPort** are not print job-specific. Between each call to a port monitor's **OpenPort** and [ClosePort](..\winsplp\nf-winsplp-closeport.md) functions, there can be multiple calls to its **StartDocPort** and **EndDocPort** functions.

You can assume that after the print spooler has called **OpenPort** with a particular port name, it will not call **OpenPort** again with the same port name before calling **ClosePort**.

Print monitor functions that accept a port handle as input do not also accept a monitor handle. Therefore, the **OpenPort** function must store the received monitor handle in a location that can be referenced by the port handle. This allows the functions that accept a port handle to reference the monitor handle.

## -see-also

[GetPrinterDataFromPort](/previous-versions/ff550506(v=vs.85))

[SetPortTimeOuts](/previous-versions/ff562630(v=vs.85))

[ClosePort](..\winsplp\nf-winsplp-closeport.md)

[StartDocPort](/previous-versions/ff562710(v=vs.85))

[OpenPortEx](/previous-versions/ff559596(v=vs.85))

[InitializePrintMonitor2](..\winsplp\nf-winsplp-initializeprintmonitor2.md)

[WritePort](..\winsplp\nf-winsplp-writeport.md)

[EndDocPort](/previous-versions/ff548742(v=vs.85))

[ReadPort](..\winsplp\nf-winsplp-readport.md)
