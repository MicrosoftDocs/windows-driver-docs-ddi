---
UID: NN:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadersFailed
title: IUsbTargetPipeContinuousReaderCallbackReadersFailed
author: windows-driver-content
description: IUsbTargetPipeContinuousReaderCallbackReadersFailed is a driver-supplied interface.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadersfailed.htm
old-project: wdf
ms.assetid: d0b68976-f7aa-4b0d-b6bb-258ad2c2e506
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iusbtargetpipecontinuousreadercallbackreadersfailed, IUsbTargetPipeContinuousReaderCallbackReadersFailed interface, IUsbTargetPipeContinuousReaderCallbackReadersFailed interface, described, IUsbTargetPipeContinuousReaderCallbackReadersFailed, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadersFailed, UMDFUSBref_c38e329c-f04a-4675-ad3b-25677fddedf9.xml, umdf.iusbtargetpipecontinuousreadercallbackreadersfailed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfusb.h
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
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	wudfusb.h
apiname: 
-	IUsbTargetPipeContinuousReaderCallbackReadersFailed
product: Windows
targetos: Windows
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IUsbTargetPipeContinuousReaderCallbackReadersFailed interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


<b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> is a driver-supplied interface.




## -members

The <b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556915">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://msdn.microsoft.com/ad91208e-e57a-4b80-b1a1-13b9f7eb1119">OnReaderFailure</a> event callback function informs the driver that a continuous reader has reported an error while processing a read request.

</td>
</tr>
</table>A driver's <a href="https://msdn.microsoft.com/ad91208e-e57a-4b80-b1a1-13b9f7eb1119">OnReaderFailure</a> event callback function informs the driver that a continuous reader has reported an error while processing a read request.

 

