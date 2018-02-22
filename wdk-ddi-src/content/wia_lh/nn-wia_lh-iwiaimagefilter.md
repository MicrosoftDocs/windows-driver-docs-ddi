---
UID: NN:wia_lh.IWiaImageFilter
title: IWiaImageFilter
author: windows-driver-content
description: The IWiaImageFilter interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).
old-location: image\iwiaimagefilter_interface.htm
old-project: Image
ms.assetid: de74898b-ac04-468d-874d-7ca281e22a86
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: image.iwiaimagefilter_interface, IWiaImageFilter interface [Imaging Devices], IWiaImageFilter interface [Imaging Devices], described, IWiaImageFilter, wia_lh/IWiaImageFilter, IWiaErrorHandler_3922a578-25ee-448c-a0db-c339711ad2cb.xml
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
-	IWiaImageFilter
product: Windows
targetos: Windows
req.typenames: "*PBMP_IMAGE_INFO, BMP_IMAGE_INFO"
req.product: Windows 10 or later.
---

# IWiaImageFilter interface


## -description


The <b>IWiaImageFilter</b> interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).


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

 

