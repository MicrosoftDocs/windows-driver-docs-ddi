---
UID: NS:ucxusbdevice._ADDRESS0_OWNERSHIP_ACQUIRE
title: "_ADDRESS0_OWNERSHIP_ACQUIRE"
author: windows-driver-content
description: Contains parameters for configuring the device.
old-location: buses\_address0_ownership_acquire.htm
old-project: usbref
ms.assetid: D2FECBA5-21DF-411C-BBDB-968328E18C12
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PADDRESS0_OWNERSHIP_ACQUIRE, ADDRESS0_OWNERSHIP_ACQUIRE, ADDRESS0_OWNERSHIP_ACQUIRE structure [Buses], P_ADDRESS0_OWNERSHIP_ACQUIRE, P_ADDRESS0_OWNERSHIP_ACQUIRE structure pointer [Buses], _ADDRESS0_OWNERSHIP_ACQUIRE, buses._address0_ownership_acquire, ucxusbdevice/P_ADDRESS0_OWNERSHIP_ACQUIRE, ucxusbdevice/_ADDRESS0_OWNERSHIP_ACQUIRE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	ADDRESS0_OWNERSHIP_ACQUIRE
product: Windows
targetos: Windows
req.typenames: ADDRESS0_OWNERSHIP_ACQUIRE, *PADDRESS0_OWNERSHIP_ACQUIRE
req.product: Windows 10 or later.
---

# _ADDRESS0_OWNERSHIP_ACQUIRE structure


## -description


Contains parameters for configuring the device. 


## -syntax


````
typedef struct _ADDRESS0_OWNERSHIP_ACQUIRE {
#if __cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} ADDRESS0_OWNERSHIP_ACQUIRE, *P_ADDRESS0_OWNERSHIP_ACQUIRE;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.

