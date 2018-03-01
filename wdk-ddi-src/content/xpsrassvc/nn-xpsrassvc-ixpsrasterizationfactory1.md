---
UID: NN:xpsrassvc.IXpsRasterizationFactory1
title: IXpsRasterizationFactory1
author: windows-driver-content
description: In Windows 8, the improvement of XPSRas to handle high precision colors has led to the development of a new interface, IXPSRasterizationFactory1.
old-location: print\xpsrasterizationfactory1.htm
old-project: print
ms.assetid: 65EFEC4F-60DC-41DF-81F2-5A5C4EEE4BF8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IXpsRasterizationFactory1, IXpsRasterizationFactory1 interface [Print Devices], IXpsRasterizationFactory1 interface [Print Devices], described, print.xpsrasterizationfactory1, xpsrassvc/IXpsRasterizationFactory1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: xpsrassvc.h
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
req.lib: xpsrassvc.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	xpsrassvc.h
api_name:
-	IXpsRasterizationFactory1
product: Windows
targetos: Windows
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---

# IXpsRasterizationFactory1 interface


## -description


In Windows 8, the improvement of XPSRas to handle high precision colors has led to the development of a new interface,  <b>IXPSRasterizationFactory1</b>. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsRasterizationFactory1</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IXpsRasterizationFactory1</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IXpsRasterizationFactory1</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn937113">CreateRasterizer</a>
</td>
<td align="left" width="63%">
The <code>CreateRasterize</code> method creates an XPS rasterizer object that can handle high precision colors.

</td>
</tr>
</table> 

