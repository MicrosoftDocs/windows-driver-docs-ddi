---
UID: NS:ntddk._KEY_VIRTUALIZATION_INFORMATION
title: _KEY_VIRTUALIZATION_INFORMATION (ntddk.h)
description: The KEY_VIRTUALIZATION_INFORMATION structure defines the basic information that is available for a registry key or subkey.
old-location: kernel\key_virtualization_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KEY_VIRTUALIZATION_INFORMATION structure"]
ms.keywords: "*PKEY_VIRTUALIZATION_INFORMATION, KEY_VIRTUALIZATION_INFORMATION, KEY_VIRTUALIZATION_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_VIRTUALIZATION_INFORMATION, PKEY_VIRTUALIZATION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_VIRTUALIZATION_INFORMATION, kernel.key_virtualization_information, kstruct_c_00c77a09-ed8d-4a66-9b18-b971c9eab5ce.xml, ntddk/KEY_VIRTUALIZATION_INFORMATION, ntddk/PKEY_VIRTUALIZATION_INFORMATION"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
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
req.typenames: KEY_VIRTUALIZATION_INFORMATION, *PKEY_VIRTUALIZATION_INFORMATION
f1_keywords:
 - _KEY_VIRTUALIZATION_INFORMATION
 - ntddk/_KEY_VIRTUALIZATION_INFORMATION
 - PKEY_VIRTUALIZATION_INFORMATION
 - ntddk/PKEY_VIRTUALIZATION_INFORMATION
 - KEY_VIRTUALIZATION_INFORMATION
 - ntddk/KEY_VIRTUALIZATION_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _KEY_VIRTUALIZATION_INFORMATION
 - PKEY_VIRTUALIZATION_INFORMATION
 - KEY_VIRTUALIZATION_INFORMATION
---

# _KEY_VIRTUALIZATION_INFORMATION structure


## -description

The <b>KEY_VIRTUALIZATION_INFORMATION</b> structure defines the basic information that is available for a registry key or subkey.

## -struct-fields

### -field VirtualizationCandidate

Specifies whether the key is part of the virtualization namespace scope.

### -field VirtualizationEnabled

Specifies whether virtualization is enabled on this key. This value can be set to 1 only if <b>VirtualizationCandidate</b> is 1.

### -field VirtualTarget

Specifies whether the key is a virtual key. This value can be set to 1 only if <b>VirtualizationCandidate</b> and <b>VirtualizationEnabled</b> are both 0. This value is valid only on the virtual store key handles.

### -field VirtualStore

Specified whether the key is a part of the virtual store path.

### -field VirtualSource

Specifies whether the key has ever been virtualized. This value can be set to 1 only if <b>VirtualizationCandidate</b> is 1.

### -field Reserved

This value is reserved for system use.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_basic_information">KEY_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_key_cached_information">KEY_CACHED_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_full_information">KEY_FULL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_information_class">KEY_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_key_name_information">KEY_NAME_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_node_information">KEY_NODE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratekey">ZwEnumerateKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwquerykey">ZwQueryKey</a>

