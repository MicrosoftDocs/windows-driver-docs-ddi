---
UID: NF:wia_lh.IWiaImageFilter.InitializeFilter
title: IWiaImageFilter::InitializeFilter (wia_lh.h)
description: The IWiaImageFilter::InitializeFilter method stores the references to pWiaItem2 and pWiaTransferCallback parameters passed into the method.
tech.root: image
ms.date: 11/10/2022
keywords: ["IWiaImageFilter::InitializeFilter"]
ms.keywords: IWiaErrorHandler_f9d42d0d-1768-4868-bd41-b20297008312.xml, IWiaImageFilter interface [Imaging Devices],InitializeFilter method, IWiaImageFilter.InitializeFilter, IWiaImageFilter::InitializeFilter, InitializeFilter, InitializeFilter method [Imaging Devices], InitializeFilter method [Imaging Devices],IWiaImageFilter interface, image.iwiaimagefilter_initializefilter, wia_lh/IWiaImageFilter::InitializeFilter
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
 - IWiaImageFilter::InitializeFilter
 - wia_lh/IWiaImageFilter::InitializeFilter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wia_lh.h
api_name:
 - IWiaImageFilter::InitializeFilter
---

## -description

The **IWiaImageFilter::InitializeFilter** method stores the references to *pWiaItem2* and *pWiaTransferCallback* parameters passed into the method.

## -parameters

### -param pWiaItem2 [in]

Points to the [**IWiaItem2**](/windows/win32/wia/-wia-iwiaitem2) item that the image acquisition was initiated for by the application. In the case of [**IWiaTransfer::Download**](/windows/win32/wia/-wia-iwiatransfer-download), it is the WIA item from which we obtained the [**IWiaTransfer**](/windows/win32/wia/-wia-iwiatransfer) interface, and in the case of the Preview component, it is the item that we pass into the [**IWiaPreview::GetNewPreview**](/windows/win32/wia/-wia-iwiapreview-getnewpreview) method.

### -param pWiaTransferCallback [in]

Points to a [**IWiaTransferCallback**](nn-wia_lh-iwiatransfercallback.md) interface. The **IWiaTransferCallback** interface is the application's callback interface, which is passed to **IWiaTransfer::Download** and **IWiaPreview::GetNewPreview**.

## -returns

Returns S_OK on success, or a standard COM error code on failure.

## -remarks

This method is called by the COM proxy object before the download call reaches the WIA service. This happens in two cases: when an application calls **IWiaTransfer::Download** method and when an application calls the **IWiaPreview::GetNewPreview** method.

All that [**IWiaImageFilter::InitializeFilter**](nf-wia_lh-iwiaimagefilter-initializefilter.md) is required to do is to store the references to *pWiaItem2* and *pWiaTransferCallback* that are passed into it. These interface pointers should be stored as member variables in this method and **AddRef** should be called for each interface pointer. These two interface pointers are needed in the filter's implementation of [**IWiaTransferCallback::TransferCallback**](/windows/win32/wia/-wia-iwiatransfercallback-transfercallback) and [**IWiaTransferCallback::GetNextStream**](nf-wia_lh-iwiatransfercallback-getnextstream.md) methods.

This method cannot be invoked directly by the application.

## -see-also

[**IWiaImageFilter**](nn-wia_lh-iwiaimagefilter.md)

[**IWiaItem2**](/windows/win32/wia/-wia-iwiaitem2)

[**IWiaPreview::GetNewPreview**](/windows/win32/wia/-wia-iwiapreview-getnewpreview)

[**IWiaTransferCallback**](nn-wia_lh-iwiatransfercallback.md)

[**IWiaTransfer::Download**](/windows/win32/wia/-wia-iwiatransfer-download)
