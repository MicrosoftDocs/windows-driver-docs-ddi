---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
title: PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
author: windows-driver-content
description: Used to calculate a private session size.
old-location: display\pfnd3d12ddi_calcprivatecryptosessionsize_0030_.htm
old-project: display
ms.assetid: 5C6A62D2-C4D1-4024-B777-EA4AAC7AC971
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_calcprivatecryptosessionsize_0030_, PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030 entry point [Display Devices], PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030, d3d12umddi/PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
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
-	PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030 callback


## -description


Used to calculate a private session size.


## -prototype


````
SIZE_T APIENTRY* PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030(
             D3D12DDI_HDEVICE                        hDrvDevice,
  _In_ const  D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 *pArgs
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to create a session.


## -returns



Returns the size of the session in bytes.



