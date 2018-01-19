---
UID: NN:wia_lh.IWiaImageFilter
title: IWiaImageFilter
author: windows-driver-content
description: The IWiaImageFilter interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).
old-location: image\iwiaimagefilter_interface.htm
old-project: image
ms.assetid: de74898b-ac04-468d-874d-7ca281e22a86
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IWiaTransferCallback, IWiaTransferCallback::TransferCallback, TransferCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wia_lh.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaImageFilter
req.alt-loc: wia_lh.h
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
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaImageFilter interface



## -description
The <b>IWiaImageFilter</b> interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaImageFilter</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWiaImageFilter</b> also has these types of members:

The <b>IWiaImageFilter</b> interface has these methods.

The <b>IWiaImageFilter::FilterPreviewImage</b> method is called by the WIA Preview component, when an application calls the <b>IWiaPreview::UpdatePreview</b> method.

The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.

 


## -members
The <b>IWiaImageFilter</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543912">IWiaImageFilter::FilterPreviewImage</a>
</td>
<td align="left" width="63%">
The <b>IWiaImageFilter::FilterPreviewImage</b> method is called by the WIA Preview component, when an application calls the <b>IWiaPreview::UpdatePreview</b> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543916">IWiaImageFilter::InitializeFilter</a>
</td>
<td align="left" width="63%">
The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.

</td>
</tr>
</table>The <b>IWiaImageFilter::FilterPreviewImage</b> method is called by the WIA Preview component, when an application calls the <b>IWiaPreview::UpdatePreview</b> method.

The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.

 


## -remarks
