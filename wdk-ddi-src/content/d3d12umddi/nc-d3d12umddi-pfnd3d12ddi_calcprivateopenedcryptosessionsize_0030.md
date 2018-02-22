---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030
title: PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030
author: windows-driver-content
description: Used to calculate the size of an opened session.
old-location: display\pfnd3d12ddi_calcprivateopenedcryptosessionsize_0030.htm
old-project: display
ms.assetid: 2BA706AC-4B00-461F-8EED-0BC3BB6E2A2C
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_calcprivateopenedcryptosessionsize_0030, PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030 entry point [Display Devices], PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030, d3d12umddi/PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030 callback


## -description


Used to calculate the size of an opened session.


## -prototype


````
SIZE_T APIENTRY* PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030(
             D3D12DDI_HDEVICE                     hDrvDevice,
  _In_ const D3D12DDIARG_OPEN_CRYPTO_SESSION_0030 *pArgs
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to open a crypto session.


## -returns



Returns the size of the session in bytes.



