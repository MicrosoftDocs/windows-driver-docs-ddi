---
UID: NN:printerextension.IPrintSchemaCapabilities2
title: IPrintSchemaCapabilities2
author: windows-driver-content
description: The IPrintSchemaCapabilities2 interface represents an extension to the IPrintSchemaCapabilities object, which provides wrapper methods over a print capabilities document.
old-location: print\iprintschemacapabilities2.htm
old-project: print
ms.assetid: 1C361DC6-6517-4845-BEA6-09D2BB3B3232
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaCapabilities2, IPrintSchemaCapabilities2 interface [Print Devices], IPrintSchemaCapabilities2 interface [Print Devices], described, print.iprintschemacapabilities2, printerextension/IPrintSchemaCapabilities2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrintSchemaCapabilities2
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities2 interface


## -description


The <b>IPrintSchemaCapabilities2</b> interface represents an extension to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object, which provides wrapper methods over a print capabilities document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>. <b>IPrintSchemaCapabilities2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintSchemaCapabilities2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn465889">GetParameterDefinition</a>
</td>
<td align="left" width="63%">
The <b>GetParameterDefinition</b> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/dn465890">IPrintSchemaParameterDefinition</a> object, and it  represents the &lt;psf:ParameterDef&gt; element in the PrintCapabilites XML.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>
 

 

