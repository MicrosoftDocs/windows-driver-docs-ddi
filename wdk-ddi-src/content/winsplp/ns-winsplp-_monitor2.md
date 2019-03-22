---
UID: NS:winsplp._MONITOR2
title: _MONITOR2 (winsplp.h)
description: The MONITOR2 structure contains pointers to the functions defined by print monitors.
old-location: print\monitor2.htm
tech.root: print
ms.assetid: 0bfb5119-2034-4e63-9fbe-e2ff42a352d6
ms.date: 03/21/2019
ms.keywords: "*LPMONITOR2, *PMONITOR2, LPMONITOR2, LPMONITOR2 structure pointer [Print Devices], MONITOR2, MONITOR2 structure [Print Devices], PMONITOR2, PMONITOR2 structure pointer [Print Devices], _MONITOR2, print.monitor2, spoolfnc_db4ec1e7-1368-4695-bae0-91fd5dcd8a1a.xml, winsplp/LPMONITOR2, winsplp/MONITOR2, winsplp/PMONITOR2"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsplp.h
api_name:
- MONITOR2
product:
- Windows
targetos: Windows
req.typenames: MONITOR2, *PMONITOR2, *LPMONITOR2
---

# _MONITOR2 structure

## -description

The MONITOR2 structure contains pointers to the functions defined by print monitors.

## -struct-fields

### -field cbSize

Specifies the size, in bytes, of the MONITOR2 structure.

### -field pfnEnumPorts

A port monitor server DLL's [EnumPorts]() function enumerates the ports that the port monitor supports.

### -field pfnOpenPort

Pointer to the print monitor's [OpenPort]() function.

### -field pfnOpenPortEx

A language monitor's [OpenPortEx]() function opens a printer port.

### -field pfnStartDocPort

A print monitor's [StartDocPort]() function performs the tasks required to start a print job on the specified port.

### -field pfnWritePort

Pointer to the print monitor's [WritePort]() function.

### -field pfnReadPort

Pointer to the print monitor's [ReadPort]() function.

### -field pfnEndDocPort

A print monitor's [EndDocPort]() function performs the tasks required to end a print job on the specified port.

### -field pfnClosePort

Pointer to the print monitor's [ClosePort]() function.

### -field pfnAddPort

The [AddPort](https://docs.microsoft.com/previous-versions/ff545022(v=vs.85)) function is obsolete and is for use only with Windows NT 4.0 and previous versions.

[AddPort](https://docs.microsoft.com/previous-versions/ff545022(v=vs.85)) creates a port and adds it to the list of ports currently supported by the specified monitor in the spooler environment.

### -field pfnAddPortEx

(Obsolete. Must be NULL.) Pointer to the print monitor's [AddPortEx](https://docs.microsoft.com/previous-versions/ff545025(v%3dvs.85)) function. (Port monitors only.)

### -field pfnConfigurePort

The [ConfigurePort]() function is obsolete and is for use only with Windows NT 4.0 and previous versions. For later versions of Windows, use [ConfigurePortUI]().

[ConfigurePort]() is a port management function that configures the specified port.

### -field pfnDeletePort

The [DeletePort]() function is obsolete and is for use only with Windows NT 4.0 and previous versions.

**DeletePort** deletes a port from the monitor's environment.

### -field pfnGetPrinterDataFromPort

Pointer to the print monitor's [GetPrinterDataFromPort]() function.

### -field pfnSetPortTimeOuts

A port monitor server DLL's <code>SetPortTimeOuts</code> function sets port time-out values for an open port.

### -field pfnXcvOpenPort

Pointer to the print monitor's [XcvOpenPort]() function. (Port monitors only.)

### -field pfnXcvDataPort

Pointer to the print monitor's [XcvDataPort]() function. (Port monitors only.)

### -field pfnXcvClosePort

Pointer to the print monitor's [XcvClosePort]() function. (Port monitors only.)

### -field pfnShutdown

Pointer to the print monitor's [Shutdown]() function.

### -field pfnSendRecvBidiDataFromPort

Pointer to the print monitor's [SendRecvBidiDataFromPort]() function.

### -field pfnNotifyUsedPorts

### -field pfnNotifyUnusedPorts

### -field pfnPowerEvent

## -remarks

Each language monitor and each port monitor server DLL must provide a MONITOR2 structure. The monitor must supply values for all structure members, and specify the structure's address as the return value for its [InitializePrintMonitor2](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-initializeprintmonitor2) function.

If a function is not defined, its pointer must be NULL.

## -see-also

[InitializePrintMonitor2](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-initializeprintmonitor2)

[MONITORUI](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/ns-winsplp-_monitorui)
