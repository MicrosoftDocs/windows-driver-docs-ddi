---
UID: NN:wia_lh.IWiaTransferCallback
title: IWiaTransferCallback (wia_lh.h)
description: The IWiaTransferCallback interface is implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).
old-location: image\iwiatransfercallback_interface.htm
tech.root: image
ms.assetid: c85e5faa-b14b-4775-a5cc-cec5e20dc974
ms.date: 05/03/2018
ms.keywords: IWiaTransferCallback, IWiaTransferCallback interface [Imaging Devices], IWiaTransferCallback interface [Imaging Devices],described, IWiaTransfercallback_ae8874d9-135f-4627-bbec-51cebd6c3d69.xml, image.iwiatransfercallback_interface, wia_lh/IWiaTransferCallback
ms.topic: interface
f1_keywords:
 - "wia_lh/IWiaTransferCallback"
req.header: wia_lh.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wia_lh.h
api_name:
- IWiaTransferCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaTransferCallback interface


## -description


The <b>IWiaTransferCallback</b> interface is implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).

This interface's methods are called as a result of an application calling <b>IWiaTransfer::Download</b> or the preview component's <b>IWiaPreview::GetNewPreview</b>.

This interface is available in Windows Vista and later operating system versions.

The methods on this interface depend on the <b>IWiaTransfer</b> and <b>IWiaPreview</b> interfaces, both of which are described in the Microsoft Windows SDK documentation.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaTransferCallback</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaTransferCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

