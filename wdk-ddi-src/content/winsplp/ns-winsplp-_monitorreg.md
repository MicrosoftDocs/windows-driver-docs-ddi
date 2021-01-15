---
UID: NS:winsplp._MONITORREG
title: _MONITORREG (winsplp.h)
description: The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.
old-location: print\monitorreg.htm
tech.root: print
ms.date: 11/04/2020
keywords: ["MONITORREG structure"]
ms.keywords: "*PMONITORREG, MONITORREG, MONITORREG structure [Print Devices], PMONITORREG, PMONITORREG structure pointer [Print Devices], _MONITORREG, print.monitorreg, spoolfnc_2d0db8db-eea5-461a-a257-1fb986001dac.xml, winsplp/MONITORREG, winsplp/PMONITORREG"
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
req.typenames: MONITORREG, *PMONITORREG
f1_keywords:
 - _MONITORREG
 - winsplp/_MONITORREG
 - PMONITORREG
 - winsplp/PMONITORREG
 - MONITORREG
 - winsplp/MONITORREG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - _MONITORREG
 - PMONITORREG
 - MONITORREG
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

The MONITORREG structure's address is supplied in a [MONITORINIT](./ns-winsplp-_monitorinit.md) structure, which is passed to a print monitor's [InitializePrintMonitor2](./nf-winsplp-initializeprintmonitor2.md) function.

When [storing port configuration information](/windows-hardware/drivers/print/storing-port-configuration-information), print monitors must not explicitly call either the Win32 registry API or the cluster registry API.

> [!NOTE]
> The spooler contains a copy of the registry. Do not use the Win32 registry API to get the value actually used by the spooler. Use the spooler registry functions listed below whose pointers are contained in the MONITORREG structure.

Instead, they must call equivalent spooler registry functions. The MONITORREG structure supplies the addresses of these functions. The following table lists each spooler registry function and its equivalent cluster registry function.

| Spooler Registry Function | Equivalent Cluster Registry Function |
|--|--|
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

Input and output parameters for these spooler functions match the parameters of the equivalent cluster registry functions in the [clusapi.h](/windows/win32/api/clusapi/index) header, with the following exceptions:

- Each spooler registry function requires an *hSpooler* input parameter. This is the spooler handle received in the [MONITORINIT](./ns-winsplp-_monitorinit.md) structure.

- The spooler registry functions use HANDLE and PHANDLE parameter types instead of the HKEY and PHKEY types used by the cluster registry functions. Monitors receive the handle of the root registry location in the **hckRegistryRoot** member of the [MONITORINIT](./ns-winsplp-_monitorinit.md) structure.

## -see-also

[InitializePrintMonitor2](./nf-winsplp-initializeprintmonitor2.md)

[MONITORINIT](./ns-winsplp-_monitorinit.md)

