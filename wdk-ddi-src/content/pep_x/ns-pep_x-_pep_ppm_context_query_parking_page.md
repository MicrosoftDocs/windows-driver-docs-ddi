---
UID: NS:pep_x._PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
title: _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE (pep_x.h)
description: The PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure describes the parking page for a processor.
old-location: kernel\pep_ppm_context_query_parking_page.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure"]
ms.keywords: "*PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure [Kernel-Mode Driver Architecture], PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, kernel.pep_ppm_context_query_parking_page, pepfx/PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, pepfx/PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE"
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
targetos: Windows
req.typenames: PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, *PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE
f1_keywords:
 - _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
 - pep_x/_PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
 - PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE
 - pep_x/PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE
 - PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
 - pep_x/PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
---

# _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure (pep_x.h)


## -description

The <b>PEP_PPM_CONTEXT_QUERY_PARKING_PAGE</b> structure describes the parking page for a processor.

## -struct-fields

### -field PhysicalPageAddress

The physical memory address of the parking page.

### -field VirtualPageAddress

The virtual memory address of the parking page.

## -remarks

The output buffer for a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_context_query_parking_page">PEP_PPM_POWER_CONTROL_QUERY_PARKING_PAGE</a> power control request is a <b>PEP_PPM_CONTEXT_QUERY_PARKING_PAGE</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_context_query_parking_page">PEP_PPM_POWER_CONTROL_QUERY_PARKING_PAGE</a>
