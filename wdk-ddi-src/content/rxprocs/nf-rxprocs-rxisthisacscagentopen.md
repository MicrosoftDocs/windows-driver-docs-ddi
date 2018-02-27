---
UID: NF:rxprocs.RxIsThisACscAgentOpen
title: RxIsThisACscAgentOpen function
author: windows-driver-content
description: RxIsThisACscAgentOpen determines if a file open was made by a user-mode client-side caching agent.
old-location: ifsk\rxisthisacscagentopen.htm
old-project: ifsk
ms.assetid: b3bd9b9f-e859-4d7f-9735-5995cb3ef6e8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxIsThisACscAgentOpen, RxIsThisACscAgentOpen function [Installable File System Drivers], ifsk.rxisthisacscagentopen, rxprocs/RxIsThisACscAgentOpen, rxref_1d515511-d1dd-4090-9c9d-b87960d56f5c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxprocs.h
apiname:
-	RxIsThisACscAgentOpen
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxIsThisACscAgentOpen function


## -description


<b>RxIsThisACscAgentOpen</b> determines if a file open was made by a user-mode client-side caching agent.


## -syntax


````
BOOLEAN RxIsThisACscAgentOpen(
  _In_ PRX_CONTEXT RxContext
);
````


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure.


## -returns



<b>RxIsThisACscAgentOpen </b>returns <b>TRUE</b> on success or <b>FALSE</b> on failure. 




## -remarks



<b>RxIsThisACscAgentOpen</b> is not useful for third-party network mini-redirectors since they cannot integrate into the existing client-side caching infrastructure.

The <b>RxIsThisACscAgentOpen</b> routine is called internally by RDBSS when initializing a V_NET_ROOT structure. A network mini-redirector integrated with client-side caching might call <b>RxIsThisACscAgentOpen</b> as part of the <b>MRxCreateVNetRoot</b> callback routine provided by the network mini-redirector. 




## -see-also

<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>



<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxIsThisACscAgentOpen function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

