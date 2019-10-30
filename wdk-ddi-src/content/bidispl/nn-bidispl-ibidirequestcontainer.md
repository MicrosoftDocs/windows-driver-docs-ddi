---
UID: NN:bidispl.IBidiRequestContainer
title: IBidiRequestContainer (bidispl.h)
description: The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests.
old-location: print\ibidirequestcontainer.htm
tech.root: print
ms.assetid: 21dfcbe8-2fc1-4495-af54-5d4c83b8bb79
ms.date: 04/20/2018
ms.keywords: IBidiRequestContainer, IBidiRequestContainer interface [Print Devices], IBidiRequestContainer interface [Print Devices],described, _win32_IBidiRequestContainer, bidispl/IBidiRequestContainer, gdi.ibidirequestcontainer, print.ibidirequestcontainer
ms.topic: interface
f1_keywords:
 - "bidispl/IBidiRequestContainer"
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
- IBidiRequestContainer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequestContainer interface


## -description


The <b>IBidiRequestContainer</b> interface allows an application or other objects to compose and retrieve a list of bidi requests.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiRequestContainer</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IBidiRequestContainer</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBidiRequestContainer</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequestcontainer-addrequest">AddRequest</a>
</td>
<td align="left" width="63%">
Adds a request to the request list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequestcontainer-getenumobject">GetEnumObject</a>
</td>
<td align="left" width="63%">
Enumerates the number of requests in the list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidirequestcontainer-getrequestcount">GetRequestCount</a>
</td>
<td align="left" width="63%">
Gets the number of requests in the list.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-spooler-components">Print Spooler Components</a>
 

 

