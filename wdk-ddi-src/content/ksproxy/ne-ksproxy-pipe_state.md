---
UID: NE:ksproxy.PIPE_STATE
title: PIPE_STATE
author: windows-driver-content
description: "."
old-location: stream\pipe_state.htm
old-project: stream
ms.assetid: A3053A39-5DB6-4DB8-89ED-63ABDB1CD16F
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PipeState_RangeFixed, PipeState_DontCare, ksproxy/PipeState_CompressionUnknown, ksproxy/PIPE_STATE, ksproxy/PipeState_DontCare, PipeState_RangeNotFixed, ksproxy/PipeState_RangeFixed, ksproxy/PipeState_RangeNotFixed, PIPE_STATE, PipeState_CompressionUnknown, PIPE_STATE enumeration [Streaming Media Devices], ksproxy/PipeState_Finalized, stream.pipe_state, PipeState_Finalized
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksproxy.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksproxy.h
apiname:
-	PIPE_STATE
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# PIPE_STATE enumeration


## -description





## -syntax


````
typedef enum  { 
  PipeState_DontCare,
  PipeState_RangeNotFixed,
  PipeState_RangeFixed,
  PipeState_CompressionUnknown,
  PipeState_Finalized
} PIPE_STATE;
````


## -enum-fields




#### - PipeState_DontCare



#### - PipeState_RangeNotFixed



#### - PipeState_RangeFixed



#### - PipeState_CompressionUnknown



#### - PipeState_Finalized


