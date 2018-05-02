---
UID: NS:pep_x._PEP_PPM_QUERY_COORDINATED_DEPENDENCY
title: "_PEP_PPM_QUERY_COORDINATED_DEPENDENCY"
author: windows-driver-content
description: The PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure describes dependencies for coordinated idle states.
old-location: kernel\pep_ppm_query_coordinated_dependency.htm
old-project: kernel
ms.assetid: B7E857ED-66FF-4A4D-849B-A15663106507
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_PPM_QUERY_COORDINATED_DEPENDENCY, PEP_PPM_QUERY_COORDINATED_DEPENDENCY, PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_COORDINATED_DEPENDENCY, PPEP_PPM_QUERY_COORDINATED_DEPENDENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_COORDINATED_DEPENDENCY, kernel.pep_ppm_query_coordinated_dependency, pepfx/PEP_PPM_QUERY_COORDINATED_DEPENDENCY, pepfx/PPEP_PPM_QUERY_COORDINATED_DEPENDENCY"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PEP_PPM_QUERY_COORDINATED_DEPENDENCY
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_COORDINATED_DEPENDENCY, *PPEP_PPM_QUERY_COORDINATED_DEPENDENCY
---

# _PEP_PPM_QUERY_COORDINATED_DEPENDENCY structure


## -description


The <b>PEP_PPM_QUERY_COORDINATED_DEPENDENCY</b> structure describes dependencies for coordinated idle states.


## -struct-fields




### -field StateIndex

[in] The index of the coordinated idle state which is having its dependencies queried.


### -field DependencyIndex

[in] The index of the dependency being queried.


### -field DependencySize

[in] The size of the <b>Dependencies</b> array.


### -field DependencySizeUsed

[out] The number of elements of the <b>Dependencies</b> array filled in by the PEP.


### -field TargetProcessor

[out] The <b>POHANDLE</b> corresponding to the processor being targeted by this dependency, or <b>NULL</b> if this is a coordinated state dependency.


### -field Options

[out] A list of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186706">PEP_COORDINATED_DEPENDENCY_OPTION</a> structures describing dependency options, one of which must be satisfied for this coordinated state to be entered.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186706">PEP_COORDINATED_DEPENDENCY_OPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186775">PEP_NOTIFY_PPM_QUERY_COORDINATED_DEPENDENCY notification</a>
 

 

