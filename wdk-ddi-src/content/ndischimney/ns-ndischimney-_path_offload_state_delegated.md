---
UID: NS:ndischimney._PATH_OFFLOAD_STATE_DELEGATED
title: "_PATH_OFFLOAD_STATE_DELEGATED"
author: windows-driver-content
description: The PATH_OFFLOAD_STATE_DELEGATED structure contains the delegated variables of a path state object.
old-location: netvista\path_offload_state_delegated.htm
old-project: netvista
ms.assetid: 3a1603ec-639f-4899-8889-3c7ed2cfe375
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PPATH_OFFLOAD_STATE_DELEGATED, PATH_OFFLOAD_STATE_DELEGATED, PATH_OFFLOAD_STATE_DELEGATED structure [Network Drivers Starting with Windows Vista], PPATH_OFFLOAD_STATE_DELEGATED, PPATH_OFFLOAD_STATE_DELEGATED structure pointer [Network Drivers Starting with Windows Vista], _PATH_OFFLOAD_STATE_DELEGATED, ndischimney/PATH_OFFLOAD_STATE_DELEGATED, ndischimney/PPATH_OFFLOAD_STATE_DELEGATED, netvista.path_offload_state_delegated, tcp_chim_struct_63dab32f-c9a5-428f-94e1-7b534d83fd50.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	PATH_OFFLOAD_STATE_DELEGATED
product:
- Windows
targetos: Windows
req.typenames: PATH_OFFLOAD_STATE_DELEGATED, *PPATH_OFFLOAD_STATE_DELEGATED
---

# _PATH_OFFLOAD_STATE_DELEGATED structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The PATH_OFFLOAD_STATE_DELEGATED structure contains the delegated variables of a path state
  object.


## -struct-fields




### -field Header

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569062">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the PATH_OFFLOAD_STATE_DELEGATED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


## -remarks



Currently there are no delegated path variables.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569062">OFFLOAD_STATE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569983">PATH_OFFLOAD_STATE_CACHED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569984">PATH_OFFLOAD_STATE_CONST</a>
 

 

