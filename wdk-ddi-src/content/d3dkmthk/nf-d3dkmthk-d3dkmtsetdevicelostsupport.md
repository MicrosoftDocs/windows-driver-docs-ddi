---
UID: NF:d3dkmthk.D3DKMTSetDeviceLostSupport
title: D3DKMTSetDeviceLostSupport function
author: windows-driver-content
description: Used to indicate that the device has lost support.
old-location: display\d3dkmtsetdevicelostsupport.htm
old-project: display
ms.assetid: 9b7469cb-d489-4428-8167-91b26e1fa348
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSetDeviceLostSupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTSetDeviceLostSupport
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSetDeviceLostSupport function



## -description

			
            Used to indicate that the device has lost support.



## -syntax

````
NTSTATUS  D3DKMTSetDeviceLostSupport(
  _In_ D3DKMT_SETDEVICELOSTSUPPORT  *D3dkmt_setdevicelostsupport
);
````


## -parameters

### -param D3dkmt_setdevicelostsupport [in]

Indicates that the device has lost support.


## -returns
Returns STATUS_SUCCESS if completed successfully. 


## -remarks
