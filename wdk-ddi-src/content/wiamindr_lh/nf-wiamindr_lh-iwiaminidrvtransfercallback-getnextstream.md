---
UID: NF:wiamindr_lh.IWiaMiniDrvTransferCallback.GetNextStream
title: IWiaMiniDrvTransferCallback::GetNextStream (wiamindr_lh.h)
description: Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).
old-location: image\iwiaminidrvtransfercallback_getnextstream.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaMiniDrvTransferCallback::GetNextStream"]
ms.keywords: GetNextStream, GetNextStream method [Imaging Devices], GetNextStream method [Imaging Devices],IWiaMiniDrvTransferCallback interface, IWiaMiniDrvTransferCallback interface [Imaging Devices],GetNextStream method, IWiaMiniDrvTransferCallback.GetNextStream, IWiaMiniDrvTransferCallback::GetNextStream, image.iwiaminidrvtransfercallback_getnextstream, wiamindr_lh/IWiaMiniDrvTransferCallback::GetNextStream
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
 - IWiaMiniDrvTransferCallback::GetNextStream
 - wiamindr_lh/IWiaMiniDrvTransferCallback::GetNextStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiamindr_lh.h
api_name:
 - IWiaMiniDrvTransferCallback::GetNextStream
---

# IWiaMiniDrvTransferCallback::GetNextStream


## -description

Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).

## -parameters

### -param lFlags 

[in]
Represents flag bits. This parameter is unused and should always be set to zero (0) by the caller.

### -param bstrItemName 

[in]
The name of the item that will perform the data transfer. For more information, see  [WIA_IPA_ITEM_NAME](/windows-hardware/drivers/image/wia-ipa-item-name).

### -param bstrFullItemName 

[in]
The full name of the item that will perform the data transfer. For more information, see [WIA_IPA_FULL_ITEM_NAME](/windows-hardware/drivers/image/wia-ipa-full-item-name).

### -param ppIStream 

[out]
A pointer to an **IStream** object.

## -returns

This method returns S_OK when the call is successful. Otherwise it returns an appropriate HRESULT error code.

## -remarks

When the client requests to skip the data transfer, the **GetNextStream** method returns WIA_STATUS_SKIP_ITEM. The WIA mini-driver must skip the current image transfer and continue with the next image transfer, if any. For example, for a download transfer, finish scanning the current image and then discard the image data.

When the current transfer sequence is cancelled, the **GetNextStream** method returns S_FALSE.

## -see-also

[Cancellation of Data Transfers](/windows-hardware/drivers/image/cancellation-of-data-transfers-in-windows-vista)

[Data Transfer Between Legacy Application and Windows Driver](/windows-hardware/drivers/image/data-transfer-between-legacy-application-and-windows-vista-driver)

[IWiaMiniDrvTransferCallback](./nn-wiamindr_lh-iwiaminidrvtransfercallback.md)

[WIA_IPA_FULL_ITEM_NAME](/windows-hardware/drivers/image/wia-ipa-full-item-name)

[WIA_IPA_ITEM_NAME](/windows-hardware/drivers/image/wia-ipa-item-name)

