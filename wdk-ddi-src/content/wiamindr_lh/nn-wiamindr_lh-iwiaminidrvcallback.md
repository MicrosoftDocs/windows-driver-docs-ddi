---
UID: NN:wiamindr_lh.IWiaMiniDrvCallBack
title: IWiaMiniDrvCallBack (wiamindr_lh.h)
description: The IWiaMiniDrvCallBack interface provides the MiniDrvCallback method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.
old-location: image\iwiaminidrvcallback_interface.htm
tech.root: image
ms.assetid: cf2460c5-325f-43c3-a1fe-5b6982234194
ms.date: 05/03/2018
keywords: ["IWiaMiniDrvCallBack interface"]
ms.keywords: CallBack_2e94f80e-dde0-4289-8911-a769a909b4d8.xml, IWiaMiniDrvCallBack, IWiaMiniDrvCallBack interface [Imaging Devices], IWiaMiniDrvCallBack interface [Imaging Devices],described, image.iwiaminidrvcallback_interface, wiamindr_lh/IWiaMiniDrvCallBack
req.header: wiamindr_lh.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWiaMiniDrvCallBack
 - wiamindr_lh/IWiaMiniDrvCallBack
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaMiniDrvCallBack
---

# IWiaMiniDrvCallBack interface


## -description

The **IWiaMiniDrvCallBack** interface provides the [MiniDrvCallback](./nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback.md) method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.

This method can also convey status information, such as the percentage of data transferred.

## -inheritance