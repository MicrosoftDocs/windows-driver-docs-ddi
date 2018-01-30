---
UID: NF:wia_lh.IWiaImageFilter.InitializeFilter
title: IWiaImageFilter::InitializeFilter method
author: windows-driver-content
description: The IWiaImageFilter::InitializeFilter method stores the references to pWiaItem2 and pWiaTransferCallback parameters passed into the method.
old-location: image\iwiaimagefilter_initializefilter.htm
old-project: image
ms.assetid: 03e359aa-4745-4961-a342-79f725468aab
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IWiaImageFilter::InitializeFilter, InitializeFilter method [Imaging Devices], IWiaImageFilter interface, IWiaImageFilter interface [Imaging Devices], InitializeFilter method, image.iwiaimagefilter_initializefilter, IWiaImageFilter, wia_lh/IWiaImageFilter::InitializeFilter, InitializeFilter method [Imaging Devices], IWiaErrorHandler_f9d42d0d-1768-4868-bd41-b20297008312.xml, InitializeFilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia_lh.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	IWiaImageFilter.InitializeFilter
product: Windows
targetos: Windows
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaImageFilter::InitializeFilter method


## -description


The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.


## -syntax


````
HRESULT InitializeFilter(
  [in] IWiaItem2              *pWiaItem2,
  [in] IWiaTransferCallback   *pWiaTransferCallback 
);
````


## -parameters




### -param pWiaItem2 [in]

Points to the <b>IWiaItem2</b> item that the image acquisition was initiated for by the application. In the case of <b>IWiaTransfer::Download</b>, it is the WIA item from which we obtained the <b>IWiaTransfer</b> interface, and in the case of the Preview component, it is the item that we pass into the <b>IWiaPreview::GetNewPreview</b> method.


### -param pWiaTransferCallback [in]

Points to a <a href="..\wia_lh\nn-wia_lh-iwiatransfercallback.md">IWiaTransferCallback</a> interface. The IWiaTransferCallback interface is the application's callback interface, which is passed to <b>IWiaTransfer::Download</b> and <b>IWiaPreview::GetNewPreview</b>. 



## -returns


Returns S_OK on success, or a standard COM error code on failure.





## -remarks


This method is called by the COM proxy object (described in the Microsoft Windows SDK documentation) before the download call reaches the WIA service. This happens in two cases: when an application calls <b>IWiaTransfer::Download</b> method and when an application calls the <b>IWiaPreview::GetNewPreview</b> method. 

All that <b>IWiaImageFilter::InitializeFilter</b> is required to do is to store the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> that are passed into it. These interface pointers should be stored as member variables in this method and <b>AddRef</b> should be called for each interface pointer. These two interface pointers are needed in the filter's implementation of <b>IWiaTransferCallback::TransferCallback</b> and <b>IWiaTransferCallback::GetNextStream</b> methods.

The <b>IWiaTransferCallback</b> and <b>IWiaPreview</b> interfaces are described in the Windows SDK documentation.

This method cannot be invoked directly by the application.

The <b>IWiaItem2, IWiaPreview</b> and <b>IWiaTransfer</b> interfaces are described in the Windows SDK documentation.



## -see-also

<a href="..\wia_lh\nn-wia_lh-iwiatransfercallback.md">IWiaTransferCallback Interface</a>

<a href="..\wia_lh\nn-wia_lh-iwiaimagefilter.md">IWiaImageFilter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaImageFilter::InitializeFilter method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

