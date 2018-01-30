---
UID: NS:ndischimney._OFFLOAD_STATE_HEADER
title: "_OFFLOAD_STATE_HEADER"
author: windows-driver-content
description: The OFFLOAD_STATE_HEADER structure serves as a header in an offload state structure.
old-location: netvista\offload_state_header.htm
old-project: netvista
ms.assetid: 9becc611-ede9-4285-b2d7-c53747d098a9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*POFFLOAD_STATE_HEADER, ndischimney/POFFLOAD_STATE_HEADER, ndischimney/OFFLOAD_STATE_HEADER, tcp_chim_struct_83829bba-2901-4b98-ba4a-4ca2fe20fc25.xml, _OFFLOAD_STATE_HEADER, OFFLOAD_STATE_HEADER structure [Network Drivers Starting with Windows Vista], POFFLOAD_STATE_HEADER, POFFLOAD_STATE_HEADER structure pointer [Network Drivers Starting with Windows Vista], OFFLOAD_STATE_HEADER, netvista.offload_state_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
-	ndischimney.h
apiname:
-	OFFLOAD_STATE_HEADER
product: Windows
targetos: Windows
req.typenames: OFFLOAD_STATE_HEADER, *POFFLOAD_STATE_HEADER
---

# _OFFLOAD_STATE_HEADER structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The OFFLOAD_STATE_HEADER structure serves as a header in an offload state structure.


## -syntax


````
typedef struct _OFFLOAD_STATE_HEADER {
  ULONG Length;
  ULONG RecognizedOptions;
} OFFLOAD_STATE_HEADER, *POFFLOAD_STATE_HEADER;
````


## -struct-fields




### -field Length

The total size, in bytes, of the offload state structure that includes the OFFLOAD_STATE_HEADER
     member. This size includes the size of the OFFLOAD_STATE_HEADER member and the other members of the
     offload state structure.


### -field RecognizedOptions

Reserved.


## -remarks


The following offload state structures include an OFFLOAD_STATE_HEADER structure:


<mshelp:link keywords="netvista.neighbor_offload_state_const" tabindex="0"><b>
       NEIGHBOR_OFFLOAD_STATE_CONST</b></mshelp:link>



<mshelp:link keywords="netvista.neighbor_offload_state_cached" tabindex="0"><b>
       NEIGHBOR_OFFLOAD_STATE_CACHED</b></mshelp:link>



<mshelp:link keywords="netvista.neighbor_offload_state_delegated" tabindex="0"><b>
       NEIGHBOR_OFFLOAD_STATE_DELEGATED</b></mshelp:link>



<a href="..\ndischimney\ns-ndischimney-_path_offload_state_const.md">PATH_OFFLOAD_STATE_CONST</a>



<a href="..\ndischimney\ns-ndischimney-_path_offload_state_cached.md">PATH_OFFLOAD_STATE_CACHED</a>



<mshelp:link keywords="netvista.path_offload_state_delegated" tabindex="0"><b>
       PATH_OFFLOAD_STATE_DELEGATED</b></mshelp:link>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_const.md">TCP_OFFLOAD_STATE_CONST</a>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_cached.md">TCP_OFFLOAD_STATE_CACHED</a>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_delegated.md">TCP_OFFLOAD_STATE_DELEGATED</a>



