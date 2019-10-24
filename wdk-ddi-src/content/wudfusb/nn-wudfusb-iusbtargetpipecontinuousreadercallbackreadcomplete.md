---
UID: NN:wudfusb.IUsbTargetPipeContinuousReaderCallbackReadComplete
title: IUsbTargetPipeContinuousReaderCallbackReadComplete (wudfusb.h)
description: IUsbTargetPipeContinuousReaderCallbackReadComplete is a driver-supplied interface.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadcomplete.htm
tech.root: wdf
ms.assetid: 953048ab-872c-4b94-8aef-bcfcb86ea4d8
ms.date: 02/26/2018
ms.keywords: IUsbTargetPipeContinuousReaderCallbackReadComplete, IUsbTargetPipeContinuousReaderCallbackReadComplete interface, IUsbTargetPipeContinuousReaderCallbackReadComplete interface,described, UMDFUSBref_bb387411-90fe-4347-910f-4c0fa535a309.xml, umdf.iusbtargetpipecontinuousreadercallbackreadcomplete, wdf.iusbtargetpipecontinuousreadercallbackreadcomplete, wudfusb/IUsbTargetPipeContinuousReaderCallbackReadComplete
ms.topic: interface
f1_keywords:
 - "wudfusb/IUsbTargetPipeContinuousReaderCallbackReadComplete"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wudfusb.h
api_name:
- IUsbTargetPipeContinuousReaderCallbackReadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# IUsbTargetPipeContinuousReaderCallbackReadComplete interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


<b>IUsbTargetPipeContinuousReaderCallbackReadComplete</b> is a driver-supplied interface.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IUsbTargetPipeContinuousReaderCallbackReadComplete</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IUsbTargetPipeContinuousReaderCallbackReadComplete</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IUsbTargetPipeContinuousReaderCallbackReadComplete</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">IUsbTargetPipeContinuousReaderCallbackReadComplete::OnReaderCompletion</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iusbtargetpipecontinuousreadercallbackreadcomplete-onreadercompletion">OnReaderCompletion</a> event callback function informs the driver that a continuous reader has successfully completed a read request.

</td>
</tr>
</table> 

