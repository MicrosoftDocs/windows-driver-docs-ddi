---
UID: NN:wiamindr_lh.IWiaMiniDrvCallBack
title: IWiaMiniDrvCallBack
author: windows-driver-content
description: The IWiaMiniDrvCallBack interface provides the MiniDrvCallback method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.
old-location: image\iwiaminidrvcallback_interface.htm
old-project: image
ms.assetid: cf2460c5-325f-43c3-a1fe-5b6982234194
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: IWiaMiniDrvTransferCallback, IWiaMiniDrvTransferCallback::SendMessage, SendMessage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaMiniDrvCallBack
req.alt-loc: wiamindr_lh.h
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

# IWiaMiniDrvCallBack interface



## -description
The <b>IWiaMiniDrvCallBack</b> interface provides the <a href="https://msdn.microsoft.com/7d1c0d8a-65db-47fd-ad6a-a83c7ed3acd9">MiniDrvCallback</a> method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.

This method can also convey status information, such as the percentage of data transferred.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaMiniDrvCallBack</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWiaMiniDrvCallBack</b> also has these types of members:

The <b>IWiaMiniDrvCallBack</b> interface has these methods.

The <a href="https://msdn.microsoft.com/7d1c0d8a-65db-47fd-ad6a-a83c7ed3acd9">MiniDrvCallback</a> method provides a callback method for WIA minidrivers to use during a callback data transfer.

 


## -members
The <b>IWiaMiniDrvCallBack</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7d1c0d8a-65db-47fd-ad6a-a83c7ed3acd9">MiniDrvCallback</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/7d1c0d8a-65db-47fd-ad6a-a83c7ed3acd9">MiniDrvCallback</a> method provides a callback method for WIA minidrivers to use during a callback data transfer.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/7d1c0d8a-65db-47fd-ad6a-a83c7ed3acd9">MiniDrvCallback</a> method provides a callback method for WIA minidrivers to use during a callback data transfer.

 


## -remarks
