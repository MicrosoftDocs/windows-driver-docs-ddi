---
UID: NN:ksproxy.IKsTopology
title: IKsTopology
author: windows-driver-content
description: The IKsTopology interface provides a method that opens topology node objects contained within a filter.
old-location: stream\ikstopology.htm
old-project: stream
ms.assetid: 418a415c-b4db-41a1-825e-66704c45e134
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsSynchronousDeviceControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsTopology
req.alt-loc: ksproxy.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
req.typenames: PIPE_STATE
---

# IKsTopology interface



## -description
The <b>IKsTopology</b> interface provides a method that opens topology node objects contained within a filter.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsTopology</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsTopology</b> also has these types of members:

The <b>IKsTopology</b> interface has these methods.

Requests a KS filter object to open a topology node object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsTopology</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsTopology</b> also has these types of members:

The <b>IKsTopology</b> interface has these methods.

Requests a KS filter object to open a topology node object.

 


## -members
The <b>IKsTopology</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/882b47c2-8fbe-4de0-8ef3-206faaf1e990">CreateNodeInstance</a>
</td>
<td align="left" width="63%">
Requests a KS filter object to open a topology node object.

</td>
</tr>
</table>Requests a KS filter object to open a topology node object.

 


## -remarks
The IID for this interface is IID_IKsTopology.

The <b>IKsTopology</b> interface is supported by filters. </p>