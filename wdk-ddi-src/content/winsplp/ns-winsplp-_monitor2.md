---
UID: NS:winsplp._MONITOR2
title: _MONITOR2 (winsplp.h)
description: The MONITOR2 structure contains pointers to the functions defined by print monitors.
old-location: print\monitor2.htm
tech.root: print
ms.assetid: 0bfb5119-2034-4e63-9fbe-e2ff42a352d6
ms.date: 03/21/2019
keywords: ["MONITOR2 structure"]
ms.keywords: "*LPMONITOR2, *PMONITOR2, LPMONITOR2, LPMONITOR2 structure pointer [Print Devices], MONITOR2, MONITOR2 structure [Print Devices], PMONITOR2, PMONITOR2 structure pointer [Print Devices], _MONITOR2, print.monitor2, spoolfnc_db4ec1e7-1368-4695-bae0-91fd5dcd8a1a.xml, winsplp/LPMONITOR2, winsplp/MONITOR2, winsplp/PMONITOR2"
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
req.typenames: MONITOR2, *PMONITOR2, *LPMONITOR2
f1_keywords:
 - _MONITOR2
 - winsplp/_MONITOR2
 - PMONITOR2
 - winsplp/PMONITOR2
 - MONITOR2
 - winsplp/MONITOR2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - MONITOR2
---

# _MONITOR2 structure


## -description

The MONITOR2 structure contains pointers to the functions defined by print monitors.

## -struct-fields

### -field cbSize

Specifies the size, in bytes, of the MONITOR2 structure.

### -field pfnEnumPorts

A port monitor server DLL's [EnumPorts](/windows/win32/printdocs/enumports) function enumerates the ports that the port monitor supports.

### -field pfnOpenPort

Pointer to the print monitor's [OpenPort](./nf-winsplp-openport.md) function.

### -field pfnOpenPortEx

A language monitor's [OpenPortEx](/previous-versions/ff559596(v=vs.85)) function opens a printer port.

### -field pfnStartDocPort

A print monitor's [StartDocPort](/previous-versions/ff562710(v=vs.85)) function performs the tasks required to start a print job on the specified port.

### -field pfnWritePort

Pointer to the print monitor's [WritePort](./nf-winsplp-writeport.md) function.

### -field pfnReadPort

Pointer to the print monitor's [ReadPort](./nf-winsplp-readport.md) function.

### -field pfnEndDocPort

A print monitor's [EndDocPort](/previous-versions/ff548742(v=vs.85)) function performs the tasks required to end a print job on the specified port.

### -field pfnClosePort

Pointer to the print monitor's [ClosePort](./nf-winsplp-closeport.md) function.

### -field pfnAddPort

> [!IMPORTANT]
> The [AddPort](/previous-versions/ff545022(v=vs.85)) function is obsolete and shoiuld not be used.

**AddPort** creates a port and adds it to the list of ports currently supported by the specified monitor in the spooler environment.

### -field pfnAddPortEx

(Obsolete. Must be NULL.) Pointer to the print monitor's [AddPortEx](/previous-versions/ff545025(v=vs.85)) function. (Port monitors only.)

### -field pfnConfigurePort

> [!IMPORTANT]
> The [ConfigurePort](/previous-versions/ff546286(v=vs.85)) function is obsolete and should not be used. Use [ConfigurePortUI](./nf-winsplp-configureportui.md) instead.

**ConfigurePort** is a port management function that configures the specified port.

### -field pfnDeletePort

> [!IMPORTANT]
> The [DeletePort](/windows/win32/printdocs/deleteport) function is obsolete and should not be used.

**DeletePort** deletes a port from the monitor's environment.

### -field pfnGetPrinterDataFromPort

Pointer to the print monitor's [GetPrinterDataFromPort](/previous-versions/ff550506(v=vs.85)) function.

### -field pfnSetPortTimeOuts

A port monitor server DLL's [SetPortTimeOuts](/previous-versions/ff562630(v=vs.85)) function sets port time-out values for an open port.

### -field pfnXcvOpenPort

Pointer to the print monitor's [XcvOpenPort](./nf-winsplp-xcvopenport.md) function. (Port monitors only.)

### -field pfnXcvDataPort

Pointer to the print monitor's [XcvDataPort](./nf-winsplp-xcvdataport.md) function. (Port monitors only.)

### -field pfnXcvClosePort

Pointer to the print monitor's [XcvClosePort](./nf-winsplp-xcvcloseport.md) function. (Port monitors only.)

### -field pfnShutdown

Pointer to the print monitor's [Shutdown](/previous-versions/ff562646(v=vs.85)) function.

### -field pfnSendRecvBidiDataFromPort

Pointer to the print monitor's [SendRecvBidiDataFromPort](/previous-versions/ff562071(v=vs.85)) function.

### -field pfnNotifyUsedPorts

Pointer to the print monitor's **NotifyUsedPorts** function.

### -field pfnNotifyUnusedPorts

Pointer to the print monitor's **NotifyUnusedPorts** function.

### -field pfnPowerEvent

Pointer to the print monitor's **PowerEvent** function.

## -remarks

Each language monitor and each port monitor server DLL must provide a MONITOR2 structure. The monitor must supply values for all structure members, and specify the structure's address as the return value for its [InitializePrintMonitor2](./nf-winsplp-initializeprintmonitor2.md) function.

If a function is not defined, its pointer must be NULL.

The **MONITOR2** structure is larger in Windows XP than it was in Windows 2000. In order to ensure that a monitor developed with the Windows XP Driver Development Kit (DDK) will install on Windows XP and Windows 2000, the monitor must do the following:

- Perform a run-time check to determine which operating system version the monitor is running on.
- If the monitor is running on Windows 2000, it must set the **cbSize** member of the MONITOR2 structure to MONITOR2_SIZE_WIN2K (defined in Winsplp.h), the size appropriate for Windows 2000 version of this structure.

The following function determines whether the current operating system version is Windows 2000.

```cpp
BOOL  Is_Win2000()
{
  OSVERSIONINFOEX osvi;
  DWORDLONG dwlConditionMask = 0;

  // Initialize the OSVERSIONINFOEX structure.

  ZeroMemory(&osvi, sizeof(OSVERSIONINFOEX));
  osvi.dwOSVersionInfoSize = sizeof(OSVERSIONINFOEX);
  osvi.dwMajorVersion = 5;
  osvi.dwMinorVersion = 0;

  // Initialize the condition mask.
  VER_SET_CONDITION( dwlConditionMask, VER_MAJORVERSION, VER_EQUAL );
  VER_SET_CONDITION( dwlConditionMask, VER_MINORVERSION, VER_EQUAL );

  // Perform the test.
  return VerifyVersionInfo(
      &osvi,
      VER_MAJORVERSION | VER_MINORVERSION,
      dwlConditionMask);
}
```

For a monitor that is loading on Windows 2000, the following code sets the MONITOR2 structure's **cbSize** member appropriately.

```cpp
if ( Is_Win2000( ) )
    Monitor2.cbSize = MONITOR2_SIZE_WIN2K;
```

## -see-also

[InitializePrintMonitor2](./nf-winsplp-initializeprintmonitor2.md)

[MONITORUI](./ns-winsplp-_monitorui.md)