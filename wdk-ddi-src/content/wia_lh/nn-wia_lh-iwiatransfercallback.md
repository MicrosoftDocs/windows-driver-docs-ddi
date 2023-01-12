---
UID: NN:wia_lh.IWiaTransferCallback
title: IWiaTransferCallback (wia_lh.h)
description: The IWiaTransferCallback interface is implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).
tech.root: image
ms.date: 11/10/2022
keywords: ["IWiaTransferCallback interface"]
ms.keywords: IWiaTransferCallback, IWiaTransferCallback interface [Imaging Devices], IWiaTransferCallback interface [Imaging Devices],described, IWiaTransfercallback_ae8874d9-135f-4627-bbec-51cebd6c3d69.xml, image.iwiatransfercallback_interface, wia_lh/IWiaTransferCallback
req.header: wia_lh.h
req.include-header: Wia_lh.h
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
 - IWiaTransferCallback
 - wia_lh/IWiaTransferCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wia_lh.h
api_name:
 - IWiaTransferCallback
---

## -description

The **IWiaTransferCallback** interface is implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).

This interface's methods are called as a result of an application calling [**IWiaTransfer::Download**](/windows/win32/wia/-wia-iwiatransfer-download) or the preview component's [**IWiaPreview::GetNewPreview**](/windows/win32/wia/-wia-iwiapreview-getnewpreview).

The methods on this interface depend on the [**IWiaTransfer**](/windows/win32/wia/-wia-iwiatransfer) and [**IWiaPreview**](/windows/win32/wia/-wia-iwiapreview) interfaces.

## -inheritance
