---
UID: NN:filterpipeline.IPartBase
title: IPartBase
author: windows-driver-content
description: The IPartBase interface is a common base for document part interfaces.
old-location: print\ipartbase.htm
old-project: print
ms.assetid: 7523990f-04de-4182-99d9-fba100bebb84
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.ipartbase, IPartBase interface [Print Devices], IPartBase interface [Print Devices], described, IPartBase, filterpipeline/IPartBase, filterpipeline_aaad898e-c110-439c-9983-fedbab82c06d.xml
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
-	IPartBase
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartBase interface


## -description


The <b>IPartBase </b>interface is a common base for document part interfaces.


## -members

The <b>IPartBase</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551852">IPartBase::GetPartCompression</a>
</td>
<td align="left" width="63%">
The <b>GetPartCompression</b> method gets the compression of the part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551857">IPartBase::GetStream</a>
</td>
<td align="left" width="63%">
The <b>GetStream</b> method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551864">IPartBase::GetUri</a>
</td>
<td align="left" width="63%">
The <b>GetUri</b> method gets the URI of the part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551870">IPartBase::SetPartCompression</a>
</td>
<td align="left" width="63%">
The <b>SetPartCompression</b> method sets the compression of the part.

</td>
</tr>
</table>The <b>GetPartCompression</b> method gets the compression of the part.

The <b>GetStream</b> method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).

The <b>GetUri</b> method gets the URI of the part.

The <b>SetPartCompression</b> method sets the compression of the part.

 

