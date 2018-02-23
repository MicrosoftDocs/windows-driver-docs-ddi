---
UID: NN:wiamindr_lh.IWiaMiniDrvTransferCallback
title: IWiaMiniDrvTransferCallback
author: windows-driver-content
description: This is a Callback interface that is called by the WIA mini-driver for stream-based transfers.
old-location: image\iwiaminidrvtransfercallback.htm
old-project: image
ms.assetid: A3D874CB-1F43-4AA0-975B-35C0C5F7A13C
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: image.iwiaminidrvtransfercallback, IWiaMiniDrvTransferCallback interface [Imaging Devices], IWiaMiniDrvTransferCallback interface [Imaging Devices], described, IWiaMiniDrvTransferCallback, wiamindr_lh/IWiaMiniDrvTransferCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wiamindr_lh.h
apiname:
-	IWiaMiniDrvTransferCallback
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaMiniDrvTransferCallback interface


## -description


This is a Callback interface that is called by the WIA mini-driver for stream-based transfers.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaMiniDrvTransferCallback</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IWiaMiniDrvTransferCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaMiniDrvTransferCallback</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj151551">GetNextStream</a>
</td>
<td align="left" width="63%">
Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj151552">SendMessage</a>
</td>
<td align="left" width="63%">
Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.

</td>
</tr>
</table> 


## -see-also

<a href="https://msdn.microsoft.com/0cdc02bf-23fe-4122-8d5f-f42c3c07da8b">Cancellation of Data Transfers in Windows Vista</a>



<a href="https://msdn.microsoft.com/83817277-3526-4f64-8e7c-7e02c8cd77bd">Data Transfer Between Legacy Application and Windows Vista Driver</a>



<a href="http://msdn.microsoft.com/windows/hardware/gg463512">Introduction to WIA 2.0</a>



<a href="https://msdn.microsoft.com/fb830522-f95e-4dd7-8c1b-de092a6c5a51">IStream Transfer Driver Example</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrvTransferCallback interface%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

