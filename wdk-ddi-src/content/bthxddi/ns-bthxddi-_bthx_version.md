---
UID: NS:bthxddi._BTHX_VERSION
title: "_BTHX_VERSION"
author: windows-driver-content
description: The BTHX_VERSION structure describes the version or versions that the transport driver supports.
old-location: bltooth\bthx_version.htm
old-project: bltooth
ms.assetid: 2C5CC5B1-52F1-4DF5-9397-E8FD4983BA25
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: BTHX_VERSION structure [Bluetooth Devices], BTHX_VERSION, bthxddi/_BTHX_VERSION, _BTHX_VERSION, *PBTHX_VERSION, bltooth.bthx_version
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthxddi.h
req.include-header: BthXDDI.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported starting with  Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	BthXDDI.h
apiname:
-	_BTHX_VERSION
product: Windows
targetos: Windows
req.typenames: BTHX_VERSION, *PBTHX_VERSION
---

# _BTHX_VERSION structure


## -description


The BTHX_VERSION structure describes the version or versions that the transport driver supports.


## -syntax


````
struct _BTHX_VERSION {
  ULONG Version;
};
````


## -struct-fields




### -field Version

Bitmask of supported versions. Currently, BTHX_DDI_VERSION_1   is the only supported version.

