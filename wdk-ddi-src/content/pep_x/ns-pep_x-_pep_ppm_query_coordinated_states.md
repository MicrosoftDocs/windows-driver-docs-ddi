---
UID: NS:pep_x._PEP_PPM_QUERY_COORDINATED_STATES
title: "_PEP_PPM_QUERY_COORDINATED_STATES"
author: windows-driver-content
description: The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_ppm_query_coordinated_states.htm
tech.root: kernel
ms.assetid: 9C7E41E8-AFB4-4421-8773-EBDA5F779364
ms.date: 4/30/2018
ms.keywords: "*PPEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_COORDINATED_STATES, PPEP_PPM_QUERY_COORDINATED_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_COORDINATED_STATES, kernel.pep_ppm_query_coordinated_states, pepfx/PEP_PPM_QUERY_COORDINATED_STATES, pepfx/PPEP_PPM_QUERY_COORDINATED_STATES"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_QUERY_COORDINATED_STATES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES
---

# _PEP_PPM_QUERY_COORDINATED_STATES structure


## -description


The <b>PEP_PPM_QUERY_COORDINATED_STATES</b> structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.


## -struct-fields




### -field Count

[in] The size of the <b>States</b> array. This will be equal to the <b>PlatformStateCount</b> returned from the query platform states notification.  


### -field States

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186707">PEP_COORDINATED_IDLE_STATE</a> structures that contains information about each coordinated idle state that the PEP supports.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186707">PEP_COORDINATED_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186776">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES notification</a>
 

 

