---
UID: NF:wia_lh.IWiaTransferCallback.GetNextStream
title: IWiaTransferCallback::GetNextStream method
author: windows-driver-content
description: The IWiaTransferCallback::GetNextStream method is implemented by an image processing filter.
old-location: image\iwiatransfercallback_getnextstream.htm
old-project: Image
ms.assetid: 025c29d3-1167-4aa3-8399-01dab5729267
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetNextStream method [Imaging Devices], IWiaTransferCallback interface, GetNextStream method [Imaging Devices], IWiaTransferCallback, image.iwiatransfercallback_getnextstream, wia_lh/IWiaTransferCallback::GetNextStream, IWiaTransferCallback interface [Imaging Devices], GetNextStream method, IWiaTransfercallback_155c3198-1ed9-46a9-b6d8-0d6029bf0803.xml, GetNextStream, IWiaTransferCallback::GetNextStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia.h
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
req.lib: wia_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wia_lh.h
apiname:
-	IWiaTransferCallback.GetNextStream
product: Windows
targetos: Windows
req.typenames: "*PBMP_IMAGE_INFO, BMP_IMAGE_INFO"
req.product: Windows 10 or later.
---

# IWiaTransferCallback::GetNextStream method


## -description


The <b>IWiaTransferCallback::GetNextStream</b> method is implemented by an image processing filter. It is called by the WIA service as a result of an application calling <b>IWiaTransfer::Download</b> or the preview component's <b>IWiaPreview::GetNewPreview</b>. The <b>IWiaTransfer</b> and <b>IWiaPreview</b> interfaces are described in the Microsoft Windows SDK documentation.


## -syntax


````
HRESULT GetNextStream(
  [in]  LONG    lFlags,
  [in]  BSTR    bstrItemName,
  [in]  BSTR    bstrFullItemName,
  [out] IStream **ppDestination
);
````


## -parameters




### -param lFlags [in]

Is reserved. Set to zero. 


### -param bstrItemName [in]

Specifies a string containing the name of the item.


### -param bstrFullItemName [in]

Specifies a string containing the full name of the item. 


### -param ppDestination [out]

Specifies a pointer to the output stream. 


## -returns



Returns S_OK if successful, or a standard COM error value otherwise. 




## -remarks



An image processing filter's implementation of <b>IWiaTransferCallback::GetNextStream</b> and <b>IWiaTransferCallback::TransferCallback</b> are called during image acquisition, when the WIA mini-driver asks for the destination stream from the client and when the mini-driver sends progress messages back to the application.

An image processing filter's implementation of <b>IWiaTransferCallback::GetNextStream</b> must delegate to the application's <b>IWiaTransferCallback::GetNextStream</b> method. The image processing filter then uses the stream returned by the application callback's <b>IWiaTransferCallback::GetNextStream</b> implementation to create its own stream (the "filtering stream") that it passes back to the WIA service. 

In its <b>IWiaTransferCallback::GetNextStream</b> implementation, the image processing filter should read which properties are needed for its image processing from the item for which the image is being acquired. The filter must not read the properties directly from the <i>pWiaItem2</i> passed into <a href="https://msdn.microsoft.com/library/windows/hardware/ff543916">IWiaImageFilter::InitializeFilter</a>; rather it must call <b>IWiaItem2::FindItemByName </b>(described in the Windows SDK documentation) on this WIA item to obtain the actual WIA item. The reason is that during a folder transfer the images acquired correspond to the child items of <i>pWiaItem2</i> rather than to <i>pWiaItem2</i> itself. 


<div class="alert"><b>Note</b>    This method is not called by the preview component during <b>IWiaPreview::UpdatePreview</b>.</div>
<div> </div>





## -see-also

<a href="..\wia_lh\nn-wia_lh-iwiatransfercallback.md">IWiaTransferCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543916">IWiaImageFilter::InitializeFilter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20IWiaTransferCallback::GetNextStream method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

