---
UID: NF:rxprocs.RxIsThisACscAgentOpen
title: RxIsThisACscAgentOpen function (rxprocs.h)
description: RxIsThisACscAgentOpen determines if a file open was made by a user-mode client-side caching agent.
old-location: ifsk\rxisthisacscagentopen.htm
tech.root: ifsk
ms.assetid: b3bd9b9f-e859-4d7f-9735-5995cb3ef6e8
ms.date: 04/16/2018
ms.keywords: RxIsThisACscAgentOpen, RxIsThisACscAgentOpen function [Installable File System Drivers], ifsk.rxisthisacscagentopen, rxprocs/RxIsThisACscAgentOpen, rxref_1d515511-d1dd-4090-9c9d-b87960d56f5c.xml
ms.topic: function
f1_keywords:
 - "rxprocs/RxIsThisACscAgentOpen"
req.header: rxprocs.h
req.include-header: Rxcontx.h, Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: The RxIsThisACscAgentOpen routine is only available on Windows Server 2003 and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxIsThisACscAgentOpen
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxIsThisACscAgentOpen function


## -description


<b>RxIsThisACscAgentOpen</b> determines if a file open was made by a user-mode client-side caching agent.


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure.


## -returns



<b>RxIsThisACscAgentOpen </b>returns <b>TRUE</b> on success or <b>FALSE</b> on failure. 




## -remarks



<b>RxIsThisACscAgentOpen</b> is not useful for third-party network mini-redirectors since they cannot integrate into the existing client-side caching infrastructure.

The <b>RxIsThisACscAgentOpen</b> routine is called internally by RDBSS when initializing a V_NET_ROOT structure. A network mini-redirector integrated with client-side caching might call <b>RxIsThisACscAgentOpen</b> as part of the <b>MRxCreateVNetRoot</b> callback routine provided by the network mini-redirector. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-v-net-root-structure">The V_NET_ROOT Structure</a>
 

 

