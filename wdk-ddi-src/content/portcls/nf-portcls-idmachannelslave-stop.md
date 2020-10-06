---
UID: NF:portcls.IDmaChannelSlave.Stop
title: IDmaChannelSlave::Stop (portcls.h)
description: The Stop method stops a subordinate DMA object that was started by a previous call to IDmaChannelSlave::Start
tech.root: audio
ms.assetid: a74e2952-38bf-4980-bc0f-cc170aa2e7b2
ms.date: 10/30/2018
keywords: ["IDmaChannelSlave::Stop"]
ms.keywords: IDmaChannelSlave::Stop, Stop, IDmaChannelSlave.Stop, IDmaChannelSlave::Stop, IDmaChannelSlave.Stop
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IDmaChannelSlave::Stop
 - portcls/IDmaChannelSlave::Stop
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDmaChannelSlave.Stop
product:
 - Windows
---

# IDmaChannelSlave::Stop


## -description

The Stop method stops a subordinate DMA object that was started by a previous call to [IDmaChannelSlave::Start](nf-portcls-idmachannelslave-start.md).

## -returns

The stop method returns NTSTATUS.  It returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

> [!NOTE]
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the [Microsoft style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

This call flushes any data remaining in the DMA controller's internal cache at the time that the DMA transfer operation is stopped.

## -see-also

[IDmaChannelSlave::Start](nf-portcls-idmachannelslave-start.md)

[IDmaChannelSlave interface](nn-portcls-idmachannelslave.md)

