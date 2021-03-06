---
UID: NS:pcivirt._SRIOV_PROXY_QUERY_LUID_OUTPUT
title: _SRIOV_PROXY_QUERY_LUID_OUTPUT (pcivirt.h)
description: Stores the local unique identifier of the SR_IOV device implementing the interface. This structure is the output buffer for the IOCTL_SRIOV_PROXY_QUERY_LUID request.
old-location: pci\sriov_proxy_query_luid_output.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["SRIOV_PROXY_QUERY_LUID_OUTPUT structure"]
ms.keywords: "*PSRIOV_PROXY_QUERY_LUID_OUTPUT, PCI.sriov_proxy_query_luid_output, SRIOV_PROXY_QUERY_LUID_OUTPUT, SRIOV_PROXY_QUERY_LUID_OUTPUT structure [Buses], _SRIOV_PROXY_QUERY_LUID_OUTPUT, pcivirt/SRIOV_PROXY_QUERY_LUID_OUTPUT"
req.header: pcivirt.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: SRIOV_PROXY_QUERY_LUID_OUTPUT, *PSRIOV_PROXY_QUERY_LUID_OUTPUT
f1_keywords:
 - _SRIOV_PROXY_QUERY_LUID_OUTPUT
 - pcivirt/_SRIOV_PROXY_QUERY_LUID_OUTPUT
 - PSRIOV_PROXY_QUERY_LUID_OUTPUT
 - pcivirt/PSRIOV_PROXY_QUERY_LUID_OUTPUT
 - SRIOV_PROXY_QUERY_LUID_OUTPUT
 - pcivirt/SRIOV_PROXY_QUERY_LUID_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - _SRIOV_PROXY_QUERY_LUID_OUTPUT
 - PSRIOV_PROXY_QUERY_LUID_OUTPUT
 - SRIOV_PROXY_QUERY_LUID_OUTPUT
---

# _SRIOV_PROXY_QUERY_LUID_OUTPUT structure


## -description

Stores the local unique
identifier of the SR_IOV device implementing the interface. This structure is the output buffer for the <a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_proxy_query_luid">IOCTL_SRIOV_PROXY_QUERY_LUID</a> request.

## -struct-fields

### -field DeviceLuid

Local unique
identifier of the SR_IOV device implementing the interface.

## -syntax

```cpp
typedef struct _SRIOV_PROXY_QUERY_LUID_OUTPUT {
  LUID  DeviceLuid;
} SRIOV_PROXY_QUERY_LUID_OUTPUT, SRIOV_PROXY_QUERY_LUID_OUTPUT;
```

## -see-also

<a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_proxy_query_luid">IOCTL_SRIOV_PROXY_QUERY_LUID</a>

