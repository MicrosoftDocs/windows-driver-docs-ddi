---
UID: NN:filterpipeline.IPrintClassObjectFactory
title: IPrintClassObjectFactory
author: windows-driver-content
description: TheIPrintClassObjectFactory interface creates print filter-related interfaces.
old-location: print\iprintclassobjectfactory.htm
old-project: print
ms.assetid: 09691b81-6488-4972-8cbc-7873e6717287
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.iprintclassobjectfactory, IPrintClassObjectFactory interface [Print Devices], IPrintClassObjectFactory interface [Print Devices], described, IPrintClassObjectFactory, filterpipeline/IPrintClassObjectFactory, filterpipeline_dfad10be-6be6-4a74-8efb-e53182e469b7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IPrintClassObjectFactory
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintClassObjectFactory interface


## -description


The<b>IPrintClassObjectFactory</b> interface creates print filter-related interfaces.


## -members

The <b>IPrintClassObjectFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551960">IPrintClassObjectFactory::GetPrintClassObject</a>
</td>
<td align="left" width="63%">
The <b>GetPrintClassObject</b> method creates a print filter-related object for a specified printer by using the IID of the interface object to create.

</td>
</tr>
</table>The <b>GetPrintClassObject</b> method creates a print filter-related object for a specified printer by using the IID of the interface object to create.

 

