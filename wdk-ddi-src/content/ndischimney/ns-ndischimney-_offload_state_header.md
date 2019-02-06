---
UID: NS:ndischimney._OFFLOAD_STATE_HEADER
title: _OFFLOAD_STATE_HEADER (ndischimney.h)
description: The OFFLOAD_STATE_HEADER structure serves as a header in an offload state structure.
old-location: netvista\offload_state_header.htm
tech.root: netvista
ms.assetid: 9becc611-ede9-4285-b2d7-c53747d098a9
ms.date: 05/02/2018
ms.keywords: "*POFFLOAD_STATE_HEADER, OFFLOAD_STATE_HEADER, OFFLOAD_STATE_HEADER structure [Network Drivers Starting with Windows Vista], POFFLOAD_STATE_HEADER, POFFLOAD_STATE_HEADER structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_STATE_HEADER, ndischimney/OFFLOAD_STATE_HEADER, ndischimney/POFFLOAD_STATE_HEADER, netvista.offload_state_header, tcp_chim_struct_83829bba-2901-4b98-ba4a-4ca2fe20fc25.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	OFFLOAD_STATE_HEADER
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_STATE_HEADER, *POFFLOAD_STATE_HEADER
---

# _OFFLOAD_STATE_HEADER structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The OFFLOAD_STATE_HEADER structure serves as a header in an offload state structure.


## -struct-fields




### -field Length

The total size, in bytes, of the offload state structure that includes the OFFLOAD_STATE_HEADER
     member. This size includes the size of the OFFLOAD_STATE_HEADER member and the other members of the
     offload state structure.


### -field RecognizedOptions

Reserved.


## -remarks



The following offload state structures include an OFFLOAD_STATE_HEADER structure:


<a href="https://msdn.microsoft.com/1c79a3d6-c365-4740-a2e0-94333b70d8cc">
       NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/5dedffa8-9745-4668-8646-0e896942b9c8">
       NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/94a35d0f-3585-45d0-bba8-0b4a8ebbe883">
       NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569984">PATH_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569983">PATH_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/3a1603ec-639f-4899-8889-3c7ed2cfe375">
       PATH_OFFLOAD_STATE_DELEGATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570938">TCP_OFFLOAD_STATE_CONST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570937">TCP_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570939">TCP_OFFLOAD_STATE_DELEGATED</a>




