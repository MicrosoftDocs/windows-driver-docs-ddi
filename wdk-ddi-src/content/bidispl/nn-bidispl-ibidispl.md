---
UID: NN:bidispl.IBidiSpl
title: IBidiSpl (bidispl.h)
description: The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests.
old-location: print\ibidispl.htm
tech.root: print
ms.assetid: 7e4a30b2-ac3a-475a-b818-455cdb7a91bf
ms.date: 04/20/2018
ms.keywords: IBidiSpl, IBidiSpl interface [Print Devices], IBidiSpl interface [Print Devices],described, _win32_IBidiSpl, bidispl/IBidiSpl, gdi.ibidispl, print.ibidispl
ms.topic: interface
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
- IBidiSpl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl interface


## -description


The <b>IBidiSpl</b> interface allows an application or other objects to send a single bidi request or a list of bidi requests.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiSpl</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IBidiSpl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBidiSpl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl-binddevice">BindDevice</a>
</td>
<td align="left" width="63%">
Binds a printer to a bidi request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl-multisendrecv">MultiSendRecv</a>
</td>
<td align="left" width="63%">
Sends a list of bidi requests.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl-sendrecv">SendRecv</a>
</td>
<td align="left" width="63%">
Sends a bidi request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl-unbinddevice">UnbindDevice</a>
</td>
<td align="left" width="63%">
Unbinds a printer.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nn-bidispl-ibidispl">IBidiSpl</a>
 

 

