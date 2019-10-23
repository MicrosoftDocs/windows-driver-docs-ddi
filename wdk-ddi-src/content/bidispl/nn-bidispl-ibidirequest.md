---
UID: NN:bidispl.IBidiRequest
title: IBidiRequest (bidispl.h)
description: The IBidiRequest interface allows an application or other objects to compose a bidi request.
old-location: print\ibidirequest.htm
tech.root: print
ms.assetid: e7b16853-7f1d-45e4-af5e-4ae9cbb9b191
ms.date: 04/20/2018
ms.keywords: IBidiRequest, IBidiRequest interface [Print Devices], IBidiRequest interface [Print Devices],described, _win32_IBidiRequest, bidispl/IBidiRequest, gdi.ibidirequest, print.ibidirequest
ms.topic: interface
f1_keywords:
 - "bidispl/IBidiRequest"
req.header: bidispl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
- Bidispl.h
api_name:
- IBidiRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequest interface


## -description


The <b>IBidiRequest</b> interface allows an application or other objects to compose a bidi request.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiRequest</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IBidiRequest</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBidiRequest</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getenumcount">GetEnumCount</a>
</td>
<td align="left" width="63%">
Gets the number of output items.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getoutputdata">GetOutputData</a>
</td>
<td align="left" width="63%">
Gets the output data coming back from the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-getresult">GetResult</a>
</td>
<td align="left" width="63%">
Gets the result code.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-setinputdata">SetInputData</a>
</td>
<td align="left" width="63%">
Sets the data to send to the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequest-setschema">SetSchema</a>
</td>
<td align="left" width="63%">
Sets the bidi schema string.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-spooler-components">Print Spooler Components</a>
 

 

