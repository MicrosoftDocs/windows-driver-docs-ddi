---
UID: NS:ehstorioctl.tagACT_AUTHZ_STATE
title: tagACT_AUTHZ_STATE
author: windows-driver-content
description: This structure describes the Addressable Command Target (ACT) authorization state.
old-location: storage\act_authz_state.htm
old-project: storage
ms.assetid: 32bb774f-b1eb-4198-8e4c-febcac83153d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: tagACT_AUTHZ_STATE, *PACT_AUTHZ_STATE, ACT_AUTHZ_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ACT_AUTHZ_STATE
req.alt-loc: EhStorIoctl.h
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
req.typenames: *PACT_AUTHZ_STATE, ACT_AUTHZ_STATE
---

# tagACT_AUTHZ_STATE structure



## -description
This structure describes the Addressable Command Target (ACT) authorization state.



## -syntax

````
typedef struct tagACT_AUTHZ_STATE {
  UCHAR   ACT;
  BOOLEAN fAuthorized;
} ACT_AUTHZ_STATE, *PACT_AUTHZ_STATE;
````


## -struct-fields

### -field ACT

This member is ignored.


### -field fAuthorized

This member may be either <b>TRUE</b> (authorized) or <b>FALSE</b> (not authorized).


## -remarks
