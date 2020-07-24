---
UID: NS:winsplp._MONITORREG
title: _MONITORREG (winsplp.h)
description: The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.
old-location: print\monitorreg.htm
tech.root: print
ms.assetid: 57c146bc-574f-4137-89bb-e891e005de05
ms.date: 04/20/2018
keywords: ["_MONITORREG structure"]
ms.keywords: "*PMONITORREG, MONITORREG, MONITORREG structure [Print Devices], PMONITORREG, PMONITORREG structure pointer [Print Devices], _MONITORREG, print.monitorreg, spoolfnc_2d0db8db-eea5-461a-a257-1fb986001dac.xml, winsplp/MONITORREG, winsplp/PMONITORREG"
f1_keywords:
 - "winsplp/MONITORREG"
 - "MONITORREG"
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
- MONITORREG
targetos: Windows
req.typenames: MONITORREG, *PMONITORREG
---

# _MONITORREG structure

## -description

The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.

## -struct-fields

### -field cbSize

Size, in bytes, of the MONITORREG structure.

### -field fpCreateKey

Pointer to a **CreateKey** spooler registry function.

### -field fpOpenKey

Pointer to an **OpenKey** spooler registry function.

### -field fpCloseKey

Pointer to a **CloseKey** spooler registry function.

### -field fpDeleteKey

Pointer to a **DeleteKey** spooler registry function.

### -field fpEnumKey

Pointer to an **EnumKey** spooler registry function.

### -field fpQueryInfoKey

Pointer to a **QueryInfoKey** spooler registry function.

### -field fpSetValue

Pointer to a **SetValue** spooler registry function.

### -field fpDeleteValue

Pointer to a **DeleteValue** spooler registry function.

### -field fpEnumValue

Pointer to an **EnumValue** spooler registry function.

### -field fpQueryValue

Pointer to a **QueryValue** spooler registry function.

## -remarks

The MONITORREG structure's address is supplied in a [MONITORINIT](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorinit) structure, which is passed to a print monitor's [InitializePrintMonitor2](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitor2) function.

When [storing port configuration information](https://docs.microsoft.com/windows-hardware/drivers/print/storing-port-configuration-information), print monitors must not explicitly call either the Win32 registry API or the cluster registry API.

Instead, they must call equivalent spooler registry functions. The MONITORREG structure supplies the addresses of these functions. The following table lists each spooler registry function and its equivalent cluster registry function.

| Spooler Registry Function | Equivalent Cluster Registry Function |
| --- | --- |
| CreateKey | ClusterRegCreateKey |
| OpenKey | ClusterRegOpenKey |
| CloseKey | ClusterRegCloseKey |
| DeleteKey | ClusterRegDeleteKey |
| EnumKey | ClusterRegEnumKey |
| QueryInfoKey | ClusterRegQueryInfoKey |
| SetValue | ClusterRegSetValue |
| DeleteValue | ClusterRegDeleteValue |
| EnumValue | ClusterRegEnumValue |
| QueryValue | ClusterRegQueryValue |

Input and output parameters for these spooler functions match the parameters of the equivalent cluster registry functions in the [clusapi.h](https://docs.microsoft.com/windows/win32/api/clusapi/index) header, with the following exceptions:

- Each spooler registry function requires an *hSpooler* input parameter. This is the spooler handle received in the [MONITORINIT](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorinit) structure.

- The spooler registry functions use HANDLE and PHANDLE parameter types instead of the HKEY and PHKEY types used by the cluster registry functions. Monitors receive the handle of the root registry location in the **hckRegistryRoot** member of the [MONITORINIT](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorinit) structure.

## -see-also

[InitializePrintMonitor2](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitor2)

[MONITORINIT](https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorinit)
