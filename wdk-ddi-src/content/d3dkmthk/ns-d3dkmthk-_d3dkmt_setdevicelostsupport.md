---
UID: NS:d3dkmthk._D3DKMT_SETDEVICELOSTSUPPORT
title: "_D3DKMT_SETDEVICELOSTSUPPORT"
author: windows-driver-content
description: Used to indicate whether a device can recover from losing a graphics device.
old-location: display\d3dkmt-setdevicelostsupport.htm
old-project: display
ms.assetid: 191ea8ac-6646-44db-88eb-54dc51afef17
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_SETDEVICELOSTSUPPORT structure [Display Devices], D3DKMT_SETDEVICELOSTSUPPORT, display.d3dkmt-setdevicelostsupport, d3dkmthk/D3DKMT_SETDEVICELOSTSUPPORT, _D3DKMT_SETDEVICELOSTSUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SETDEVICELOSTSUPPORT
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETDEVICELOSTSUPPORT
---

# _D3DKMT_SETDEVICELOSTSUPPORT structure


## -description


Used to indicate whether a device can recover from losing a graphics device.


## -syntax


````
typedef struct _D3DKMT_SETDEVICELOSTSUPPORT {
  D3DKMT_HANDLE hDevice;
  BOOLEAN       Support;
} D3DKMT_SETDEVICELOSTSUPPORT;
````


## -struct-fields




### -field hDevice

A handle to the device.


### -field Support

Indicates whether or not the device can recover from losing the graphics device.

