---
UID: NN:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadersFailed
title: IUsbTargetPipeContinuousReaderCallbackReadersFailed
author: windows-driver-content
description: IUsbTargetPipeContinuousReaderCallbackReadersFailed is a driver-supplied interface.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadersfailed.htm
old-project: wdf
ms.assetid: d0b68976-f7aa-4b0d-b6bb-258ad2c2e506
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IUsbTargetPipeContinuousReaderCallbackReadersFailed, IUsbTargetPipeContinuousReaderCallbackReadersFailed interface, IUsbTargetPipeContinuousReaderCallbackReadersFailed interface,described, UMDFUSBref_c38e329c-f04a-4675-ad3b-25677fddedf9.xml, umdf.iusbtargetpipecontinuousreadercallbackreadersfailed, wdf.iusbtargetpipecontinuousreadercallbackreadersfailed, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadersFailed
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wudfusb.h
api_name:
-	IUsbTargetPipeContinuousReaderCallbackReadersFailed
product: Windows
targetos: Windows
req.typenames: 
---

# IUsbTargetPipeContinuousReaderCallbackReadersFailed interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


<b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> is a driver-supplied interface.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

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
</table> 

