---
UID: NN:filterpipeline.IInterFilterCommunicator
title: IInterFilterCommunicator (filterpipeline.h)
description: The IInterFilterCommunicator interface is implemented in an object that resides in the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface.
old-location: print\iinterfiltercommunicator.htm
tech.root: print
ms.assetid: 777da1db-5522-48fc-bf35-8e6bf9203d6a
ms.date: 04/20/2018
ms.keywords: IInterFilterCommunicator, IInterFilterCommunicator interface [Print Devices], IInterFilterCommunicator interface [Print Devices],described, filterpipeline/IInterFilterCommunicator, filterpipeline_80929d81-f333-4d23-9e46-72682784f0a2.xml, print.iinterfiltercommunicator
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IInterFilterCommunicator
product:
- Windows
targetos: Windows
req.typenames: 
---

# IInterFilterCommunicator interface


## -description


The <b>IInterFilterCommunicator</b> interface is implemented in an object that resides in the PrintFilterPipelineSvc service and is made available to filters through methods in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554286">IPrintPipelineFilter</a> interface.<b>IInterFilterCommunicator</b> inherits from the <b>IUnknown</b> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IInterFilterCommunicator</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IInterFilterCommunicator</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IInterFilterCommunicator</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551054">IInterFilterCommunicator::RequestReader</a>
</td>
<td align="left" width="63%">
The <b>RequestReader</b> method retrieves the reader interface for an <b>IInterFilterCommunicator</b> object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551057">IInterFilterCommunicator::RequestWriter</a>
</td>
<td align="left" width="63%">
The <b>RequestWriter</b> method retrieves the writer interface for an <b>IInterFilterCommunicator</b> object.

</td>
</tr>
</table> 

