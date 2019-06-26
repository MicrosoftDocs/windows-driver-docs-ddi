---
UID: NS:pep_x._PEP_PPM_QUERY_STATE_NAME
title: _PEP_PPM_QUERY_STATE_NAME (pep_x.h)
description: The PEP_PPM_QUERY_STATE_NAME structure contains information about a specific coordinated or platform idle state.
old-location: kernel\pep_ppm_query_state_name.htm
tech.root: kernel
ms.assetid: CE0C4DAA-0B14-4CC3-B75A-66329A5830E7
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_QUERY_STATE_NAME, PEP_PPM_QUERY_STATE_NAME, PEP_PPM_QUERY_STATE_NAME structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_STATE_NAME, PPEP_PPM_QUERY_STATE_NAME structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_STATE_NAME, kernel.pep_ppm_query_state_name, pepfx/PEP_PPM_QUERY_STATE_NAME, pepfx/PPEP_PPM_QUERY_STATE_NAME"
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_PPM_QUERY_STATE_NAME
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_STATE_NAME, *PPEP_PPM_QUERY_STATE_NAME
---

# _PEP_PPM_QUERY_STATE_NAME structure


## -description


The <b>PEP_PPM_QUERY_STATE_NAME</b> structure contains information about a specific coordinated or platform idle state. 


## -struct-fields




### -field StateIndex

[in] The index of the state that the OS is querying about.


### -field NameSize

[in/out] If <b>Name</b> is <b>NULL</b>, returns the size of the buffer required to hold <b>Name</b> (including the trailing <b>UNICODE_NULL</b> character), in WCHARs.
If <b>Name</b> is not <b>NULL</b>, supplies the size of the <b>Name</b> buffer, in WCHARs.   



### -field Name

[in] A pointer to a buffer to copy the name of the state to, or <b>NULL</b>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATE_NAME notification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">PEP_NOTIFY_PPM_QUERY_PROCESSOR_STATE_NAME notification</a>
 

 

