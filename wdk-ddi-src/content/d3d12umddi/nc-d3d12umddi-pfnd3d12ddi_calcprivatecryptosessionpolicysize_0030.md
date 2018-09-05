---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030
title: PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030
author: windows-driver-content
description: Used to calculate a session policy size.
old-location: display\pfnd3d12ddi_calcprivatecryptosessionpolicysize_0030_.htm
ms.assetid: 5FAF1FBE-DCCA-4D92-BB8D-C014D488353B
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030, PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030  entry, PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030, display.pfnd3d12ddi_calcprivatecryptosessionpolicysize_0030_
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030 callback function


## -description


Used to calculate a session policy size.


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to create a session policy.


### -param hDrvCryptoSession

The information for the driver session.


## -returns



Returns STATUS_SUCCESS if completed successfully.



