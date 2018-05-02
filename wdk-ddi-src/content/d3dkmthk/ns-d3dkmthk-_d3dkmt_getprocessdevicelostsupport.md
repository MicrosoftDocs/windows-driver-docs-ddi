---
UID: NS:d3dkmthk._D3DKMT_GETPROCESSDEVICELOSTSUPPORT
title: "_D3DKMT_GETPROCESSDEVICELOSTSUPPORT"
author: windows-driver-content
description: Used to get the indicated process.
old-location: display\d3dkmt-getprocessdevicelostsupport.htm
old-project: display
ms.assetid: 726a4f12-3cee-4d95-89d3-39f2bb357967
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_GETPROCESSDEVICELOSTSUPPORT, D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure [Display Devices], _D3DKMT_GETPROCESSDEVICELOSTSUPPORT, d3dkmthk/D3DKMT_GETPROCESSDEVICELOSTSUPPORT, display.d3dkmt-getprocessdevicelostsupport
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
req.max-support: Windows 10, version 1709
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
-	d3dkmthk.h
api_name:
-	D3DKMT_GETPROCESSDEVICELOSTSUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_GETPROCESSDEVICELOSTSUPPORT
---

# _D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to get the indicated process.


## -struct-fields




### -field hProcess

A handle to the process.


### -field AdapterLuid

LUID of Adapter that is potentially being detached


### -field Support

Indicates whether or not all devices of the process using the adapter can recover from graphics device lost.

