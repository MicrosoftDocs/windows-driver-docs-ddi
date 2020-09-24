---
UID: NS:hwnclx._CLIENT_DEVICE_INFORMATION
title: _CLIENT_DEVICE_INFORMATION (hwnclx.h)
description: The CLIENT_DEVICE_INFORMATION structure is used by the hardware notification callback HWN_CLIENT_QUERY_DEVICE_INFORMATION to return the total number of hardware notifications that the client device driver provides.
old-location: gpiobtn\_client_device_information.htm
tech.root: gpiobtn
ms.assetid: ae438f89-27b7-423f-9f82-b103ba70b7b5
ms.date: 02/15/2018
keywords: ["CLIENT_DEVICE_INFORMATION structure"]
ms.keywords: "*PCLIENT_DEVICE_INFORMATION, CLIENT_DEVICE_INFORMATION, CLIENT_DEVICE_INFORMATION structure, _CLIENT_DEVICE_INFORMATION, gpiobtn._client_device_information, hwnclx/CLIENT_DEVICE_INFORMATION"
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: CLIENT_DEVICE_INFORMATION, *PCLIENT_DEVICE_INFORMATION
f1_keywords:
 - _CLIENT_DEVICE_INFORMATION
 - hwnclx/_CLIENT_DEVICE_INFORMATION
 - PCLIENT_DEVICE_INFORMATION
 - hwnclx/PCLIENT_DEVICE_INFORMATION
 - CLIENT_DEVICE_INFORMATION
 - hwnclx/CLIENT_DEVICE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hwnclx.h
api_name:
 - CLIENT_DEVICE_INFORMATION
---

# _CLIENT_DEVICE_INFORMATION structure


## -description

The <b>CLIENT_DEVICE_INFORMATION</b> structure is used by the hardware notification callback <a href="..\hwnclx\nc-hwnclx-hwn_client_query_device_information.md">HWN_CLIENT_QUERY_DEVICE_INFORMATION</a> to return the total number of hardware notifications that the client device driver provides.

## -struct-fields

### -field Version

Specifies the version number of this structure. This value must be provided by the client driver to the class extension. The class extension is responsible for verifying that this version is supported. The hardware notification payload version number is <b>HWN_DEVICE_INFORMATION_VERSION</b>.

### -field Size

The size, in bytes, of the <b>CLIENT_DEVICE_INFORMATION</b> data structure.

### -field TotalHwNs

The total number of hardware notifications that the client device driver provides.

## -syntax

```cpp
typedef struct _CLIENT_DEVICE_INFORMATION {
  USHORT  Version;
  USHORT  Size;
  USHORT  TotalHwNs;
} CLIENT_DEVICE_INFORMATION, CLIENT_DEVICE_INFORMATION;
```

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/index">Hardware notifications reference</a>