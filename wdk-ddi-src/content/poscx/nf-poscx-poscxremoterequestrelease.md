---
UID: NF:poscx.PosCxRemoteRequestRelease
title: PosCxRemoteRequestRelease function (poscx.h)
description: PosCxRemoteRequestRelease is called whenever a remote device asks for the device to release. This initiates claim negotiation.
old-location: pos\poscxremoterequestrelease.htm
tech.root: pos
ms.assetid: 1755E30C-15F8-41A9-9F4C-26455C92B66A
ms.date: 02/23/2018
ms.keywords: PosCxRemoteRequestRelease, PosCxRemoteRequestRelease function, pos.poscxremoterequestrelease, poscx/PosCxRemoteRequestRelease
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
-	poscx.h
api_name:
-	PosCxRemoteRequestRelease
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxRemoteRequestRelease function


## -description


PosCxRemoteRequestRelease is called whenever a remote device asks for
      the device to release.  This initiates claim negotiation.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param deviceInterfaceTag [in]

The device interface that initiated the release request.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The device will now start resolving the remote request to release.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
</table>
 



