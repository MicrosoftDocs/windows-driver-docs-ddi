---
UID: NN:wiamindr_lh.IWiaMiniDrvTransferCallback
title: IWiaMiniDrvTransferCallback
author: windows-driver-content
description: This is a Callback interface that is called by the WIA mini-driver for stream-based transfers.
old-location: image\iwiaminidrvtransfercallback.htm
old-project: image
ms.assetid: A3D874CB-1F43-4AA0-975B-35C0C5F7A13C
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IWiaMiniDrvTransferCallback, IWiaMiniDrvTransferCallback::SendMessage, SendMessage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wiamindr_lh.h
req.include-header: Wiamindr_lh.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaMiniDrvTransferCallback
req.alt-loc: Wiamindr_lh.h
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
req.typenames: *PSCANWINDOW, SCANWINDOW
req.product: Windows 10 or later.
---

# IWiaMiniDrvTransferCallback interface



## -description
This is a Callback interface that is called by the WIA mini-driver for stream-based transfers.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaMiniDrvTransferCallback</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWiaMiniDrvTransferCallback</b> also has these types of members:

The <b>IWiaMiniDrvTransferCallback</b> interface has these methods.

Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).

Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.

 


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
</table>Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).

Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/0cdc02bf-23fe-4122-8d5f-f42c3c07da8b">Cancellation of Data Transfers in Windows Vista</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/83817277-3526-4f64-8e7c-7e02c8cd77bd">Data Transfer Between Legacy Application and Windows Vista Driver</a>
</dt>
<dt><a href="http://msdn.microsoft.com/windows/hardware/gg463512">Introduction to WIA 2.0</a></dt>
<dt>
<a href="https://msdn.microsoft.com/fb830522-f95e-4dd7-8c1b-de092a6c5a51">IStream Transfer Driver Example</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrvTransferCallback interface%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

