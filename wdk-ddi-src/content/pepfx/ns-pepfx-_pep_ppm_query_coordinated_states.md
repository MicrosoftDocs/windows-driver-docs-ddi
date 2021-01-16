---
UID: NS:pepfx._PEP_PPM_QUERY_COORDINATED_STATES
title: _PEP_PPM_QUERY_COORDINATED_STATES (pepfx.h)
description: The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_ppm_query_coordinated_states.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_QUERY_COORDINATED_STATES structure"]
ms.keywords: "*PPEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_COORDINATED_STATES, PPEP_PPM_QUERY_COORDINATED_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_COORDINATED_STATES, kernel.pep_ppm_query_coordinated_states, pepfx/PEP_PPM_QUERY_COORDINATED_STATES, pepfx/PPEP_PPM_QUERY_COORDINATED_STATES"
req.header: pepfx.h
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
targetos: Windows
req.typenames: PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES
f1_keywords:
 - _PEP_PPM_QUERY_COORDINATED_STATES
 - pepfx/_PEP_PPM_QUERY_COORDINATED_STATES
 - PPEP_PPM_QUERY_COORDINATED_STATES
 - pepfx/PPEP_PPM_QUERY_COORDINATED_STATES
 - PEP_PPM_QUERY_COORDINATED_STATES
 - pepfx/PEP_PPM_QUERY_COORDINATED_STATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PPM_QUERY_COORDINATED_STATES
 - PPEP_PPM_QUERY_COORDINATED_STATES
 - PEP_PPM_QUERY_COORDINATED_STATES
---

# _PEP_PPM_QUERY_COORDINATED_STATES structure (pepfx.h)


## -description

The <b>PEP_PPM_QUERY_COORDINATED_STATES</b> structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.

## -struct-fields

### -field Count

[in] The size of the <b>States</b> array. This will be equal to the <b>PlatformStateCount</b> returned from the query platform states notification.

### -field States

[out] An array of <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_coordinated_idle_state">PEP_COORDINATED_IDLE_STATE</a> structures that contains information about each coordinated idle state that the PEP supports.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_coordinated_idle_state">PEP_COORDINATED_IDLE_STATE</a>



<a href="/windows-hardware/drivers/ddi/index">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES notification</a>

