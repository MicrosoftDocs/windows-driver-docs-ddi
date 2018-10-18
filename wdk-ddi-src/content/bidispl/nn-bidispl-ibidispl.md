---
UID: NN:bidispl.IBidiSpl
title: IBidiSpl
author: windows-driver-content
description: The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests.
old-location: print\ibidispl.htm
tech.root: print
ms.assetid: 7e4a30b2-ac3a-475a-b818-455cdb7a91bf
ms.date: 4/20/2018
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Bidispl.h
api_name:
-	IBidiSpl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl interface


## -description


The <b>IBidiSpl</b> interface allows an application or other objects to send a single bidi request or a list of bidi requests.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiSpl</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IBidiSpl</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/880ff314-c79d-4395-83ad-ce61bb8da5b5">BindDevice</a>
</td>
<td align="left" width="63%">
Binds a printer to a bidi request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/d61d7f58-281c-4c82-a579-aaedbf507bae">MultiSendRecv</a>
</td>
<td align="left" width="63%">
Sends a list of bidi requests.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0c91abd0-5e49-4e23-a50f-9d1dacf9d868">SendRecv</a>
</td>
<td align="left" width="63%">
Sends a bidi request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4c294d1d-5a37-4ea4-b50f-447260e885b1">UnbindDevice</a>
</td>
<td align="left" width="63%">
Unbinds a printer.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144980">IBidiSpl</a>
 

 

