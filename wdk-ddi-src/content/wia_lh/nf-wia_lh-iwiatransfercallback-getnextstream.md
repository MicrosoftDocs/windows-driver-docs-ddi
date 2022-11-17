---
UID: NF:wia_lh.IWiaTransferCallback.GetNextStream
title: IWiaTransferCallback::GetNextStream (wia_lh.h)
description: The IWiaTransferCallback::GetNextStream method is implemented by an image processing filter.
tech.root: image
ms.date: 11/17/2022
keywords: ["IWiaTransferCallback::GetNextStream"]
ms.keywords: GetNextStream, GetNextStream method [Imaging Devices], GetNextStream method [Imaging Devices],IWiaTransferCallback interface, IWiaTransferCallback interface [Imaging Devices],GetNextStream method, IWiaTransferCallback.GetNextStream, IWiaTransferCallback::GetNextStream, IWiaTransfercallback_155c3198-1ed9-46a9-b6d8-0d6029bf0803.xml, image.iwiatransfercallback_getnextstream, wia_lh/IWiaTransferCallback::GetNextStream
req.header: wia_lh.h
req.include-header: Wia_lh.h
req.target-type: Desktop
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
 - IWiaTransferCallback::GetNextStream
 - wia_lh/IWiaTransferCallback::GetNextStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wia_lh.h
api_name:
 - IWiaTransferCallback::GetNextStream
---

## -description

The **IWiaTransferCallback::GetNextStream** method is implemented by an image processing filter. It is called by the WIA service as a result of an application calling [**IWiaTransfer::Download**](/windows/win32/wia/-wia-iwiatransfer-download) or the preview component's **IWiaPreview::GetNewPreview**](/windows/win32/wia/-wia-iwiapreview-getnewpreview).

## -parameters

### -param lFlags [in]

Reserved, set to zero.

### -param bstrItemName [in]

Specifies a string containing the name of the item.

### -param bstrFullItemName [in]

Specifies a string containing the full name of the item.

### -param ppDestination [out]

Specifies a pointer to the output stream.

## -returns

Returns S_OK if successful, or a standard COM error value otherwise.

## -remarks

An image processing filter's implementation of **IWiaTransferCallback::GetNextStream** and **IWiaTransferCallback::TransferCallback** are called during image acquisition, when the WIA mini-driver asks for the destination stream from the client and when the mini-driver sends progress messages back to the application.

An image processing filter's implementation of **IWiaTransferCallback::GetNextStream** must delegate to the application's **IWiaTransferCallback::GetNextStream** method. The image processing filter then uses the stream returned by the application callback's **IWiaTransferCallback::GetNextStream** implementation to create its own stream (the "filtering stream") that it passes back to the WIA service.

In its **IWiaTransferCallback::GetNextStream** implementation, the image processing filter should read which properties are needed for its image processing from the item for which the image is being acquired. The filter must not read the properties directly from the *pWiaItem2* passed into [**IWiaImageFilter::InitializeFilter**](nf-wia_lh-iwiaimagefilter-initializefilter.md); rather it must call **IWiaItem2::FindItemByName**](/windows/win32/wia/-wia-iwiaitem2-finditembyname) on this WIA item to obtain the actual WIA item. The reason is that during a folder transfer the images acquired correspond to the child items of *pWiaItem2* rather than to *pWiaItem2* itself.

> [!NOTE]
> This method is not called by the preview component during [**IWiaPreview::UpdatePreview**](/windows/win32/wia/-wia-iwiapreview-updatepreview).

## -see-also

[**IWiaImageFilter::InitializeFilter**](nf-wia_lh-iwiaimagefilter-initializefilter.md)

[**IWiaTransferCallback**](nn-wia_lh-iwiatransfercallback.md)
