---
UID: NN:wia_lh.IWiaErrorHandler
title: IWiaErrorHandler (wia_lh.h)
description: The IWiaErrorHandler interface provides the GetStatusDescription and ReportStatus methods, which enable minidrivers to give users information about status or errors during a data transfer and possibly give an opportunity to recover from errors.
old-location: image\iwiaerrorhandler_interface.htm
tech.root: image
ms.assetid: b441fbca-75fe-4b9d-a9d5-2ad5a4a55801
ms.date: 05/03/2018
ms.keywords: IWiaErrorHandler, IWiaErrorHandler interface [Imaging Devices], IWiaErrorHandler interface [Imaging Devices],described, IWiaErrorHandler_0a501695-14b7-4aab-aee8-19ce74caea94.xml, image.iwiaerrorhandler_interface, wia_lh/IWiaErrorHandler
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wia_lh.h
api_name:
- IWiaErrorHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaErrorHandler interface


## -description


The <b>IWiaErrorHandler</b> interface provides the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaerrorhandler-getstatusdescription">GetStatusDescription</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaerrorhandler-reportstatus">ReportStatus</a> methods, which enable minidrivers to give users information about status or errors during a data transfer and possibly give an opportunity to recover from errors.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaErrorHandler</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaErrorHandler</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaErrorHandler</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaerrorhandler-getstatusdescription">GetStatusDescription</a>
</td>
<td align="left" width="63%">
 The system UI calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaerrorhandler-getstatusdescription">GetStatusDescription</a> method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaerrorhandler-reportstatus">IWiaErrorHandler::ReportStatus</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaerrorhandler-reportstatus">ReportStatus</a> method displays information about an error or status during a transfer. In some cases this method allows the user to recover from an error.

</td>
</tr>
</table> 

