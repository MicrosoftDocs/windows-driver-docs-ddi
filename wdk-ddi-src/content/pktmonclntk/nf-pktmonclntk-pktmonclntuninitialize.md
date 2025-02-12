---
UID: NF:pktmonclntk.PktMonClntUninitialize
tech.root: 
title: PktMonClntUninitialize
ms.date: 02/10/2025
targetos: Windows
description: The PktMonClntUninitialize function uninitializes the kernel driver that is acting as a Packet Monitor client.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - PktMonClntUninitialize
f1_keywords:
 - PktMonClntUninitialize
 - pktmonclntk/PktMonClntUninitialize
dev_langs:
 - c++
helpviewer_keywords:
 - PktMonClntUninitialize
---

## -description

The **PktMonClntUninitialize** function uninitializes the kernel driver that is acting as a Packet Monitor client and was previously initialized through [PktMonClntInitialize](nf-pktmonclntk-pktmonclntinitialize.md).

## -remarks

This function will unregister components that were previously registered by the client and have not been unregistered up to that point. This allows Packet Monitor to free resources that will not be used anymore.

## -see-also

- [PktMonClntUninitialize](nf-pktmonclntk-pktmonclntuninitialize.md)
