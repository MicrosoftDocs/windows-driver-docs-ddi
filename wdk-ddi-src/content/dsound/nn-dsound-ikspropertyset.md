---
UID: NN:dsound.IKsPropertySet
title: IKsPropertySet
author: windows-driver-content
description: The IKsPropertySet interface provides methods that access properties of KS objects that are implemented in a KS minidriver.
old-location: stream\ikspropertyset.htm
old-project: stream
ms.assetid: 9999d6ec-977c-4425-ad38-0c5478272c76
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsPropertySet, IKsPropertySet::Set, Set
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dsound.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsPropertySet
req.alt-loc: dsound.h
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
req.typenames: DRMRIGHTS, *PDRMRIGHTS
---

# IKsPropertySet interface



## -description
The <b>IKsPropertySet</b> interface provides methods that access properties of KS objects that are implemented in a KS minidriver.

The IID for this interface is IID_IKsPropertySet.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPropertySet</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsPropertySet</b> also has these types of members:

The <b>IKsPropertySet</b> interface has these methods.

Retrieves a property.

Determines the support of a property.

Sets a property.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPropertySet</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsPropertySet</b> also has these types of members:

The <b>IKsPropertySet</b> interface has these methods.

Retrieves a property.

Determines the support of a property.

Sets a property.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPropertySet</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsPropertySet</b> also has these types of members:

The <b>IKsPropertySet</b> interface has these methods.

Retrieves a property.

Determines the support of a property.

Sets a property.

 


## -members
The <b>IKsPropertySet</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a>
</td>
<td align="left" width="63%">
Retrieves a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8b59da4f-0beb-46e8-913d-b992fa9f694d">QuerySupported</a>
</td>
<td align="left" width="63%">
Determines the support of a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544503">Set</a>
</td>
<td align="left" width="63%">
Sets a property.

</td>
</tr>
</table>Retrieves a property.

Determines the support of a property.

Sets a property.

 


## -remarks
The <b>IKsPropertySet</b> interface methods translate user-mode property requests into kernel-mode property sets that are used by KS minidrivers. 

KS objects include, for example, KS filters, KS pins, and KS clocks. </p>