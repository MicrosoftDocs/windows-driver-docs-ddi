---
UID: NN:printerextension.IPrinterExtensionRequest
title: IPrinterExtensionRequest
author: windows-driver-content
description: Completes the given extension event with either a cancellation or success.
old-location: print\iprinterextensionrequest_interface.htm
old-project: print
ms.assetid: 0EF8652F-34A8-4804-9D3F-8C8BEFCBCAAF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionRequest, IPrinterExtensionRequest interface [Print Devices], IPrinterExtensionRequest interface [Print Devices], described, print.iprinterextensionrequest_interface, printerextension/IPrinterExtensionRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Printerextension.h
api_name:
-	IPrinterExtensionRequest
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionRequest interface


## -description


Completes the given extension event with either a cancellation  or success.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionRequest</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterExtensionRequest</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterExtensionRequest</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a>
</td>
<td align="left" width="63%">
Completes the extension event with a cancellation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406719">Complete</a>
</td>
<td align="left" width="63%">
Completes the extension event.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973207">IPrinterExtensionEventArgs</a>



<a href="https://msdn.microsoft.com/2F11C510-B649-4DC6-B0BC-89C4159E464C">IPrinterExtensionEventArgs::Request</a>
 

 

