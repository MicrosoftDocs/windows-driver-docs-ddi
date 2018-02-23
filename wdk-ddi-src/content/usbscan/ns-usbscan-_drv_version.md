---
UID: NS:usbscan._DRV_VERSION
title: "_DRV_VERSION"
author: windows-driver-content
description: The DRV_VERSION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_VERSION.
old-location: image\drv_version.htm
old-project: image
ms.assetid: 61b6dbd3-7565-4d63-bcc0-007df9793398
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DRV_VERSION, PDRV_VERSION, _DRV_VERSION, *PDRV_VERSION, PDRV_VERSION structure pointer [Imaging Devices], stifnc_99059efa-8e64-49f6-bebe-560d33fca145.xml, DRV_VERSION structure [Imaging Devices], usbscan/PDRV_VERSION, image.drv_version, usbscan/DRV_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbscan.h
apiname:
-	DRV_VERSION
product: Windows
targetos: Windows
req.typenames: DRV_VERSION, *PDRV_VERSION
req.product: Windows 10 or later.
---

# _DRV_VERSION structure


## -description


The DRV_VERSION structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_get_version.md">IOCTL_GET_VERSION</a>.


## -syntax


````
typedef struct _DRV_VERSION {
  unsigned major;
  unsigned minor;
  unsigned internal;
} DRV_VERSION, *PDRV_VERSION;
````


## -struct-fields




### -field major

Major version number.


### -field minor

Minor version number.


### -field internal

Internal, vendor-specific version number.

