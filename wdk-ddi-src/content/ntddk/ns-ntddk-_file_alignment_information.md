---
UID: NS:ntddk._FILE_ALIGNMENT_INFORMATION
title: _FILE_ALIGNMENT_INFORMATION (ntddk.h)
description: The FILE_ALIGNMENT_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine.
old-location: kernel\file_alignment_information.htm
tech.root: kernel
ms.assetid: d3990d67-aa0c-4d17-9126-80fdcebbd306
ms.date: 04/30/2018
keywords: ["_FILE_ALIGNMENT_INFORMATION structure"]
ms.keywords: "*PFILE_ALIGNMENT_INFORMATION, FILE_ALIGNMENT_INFORMATION, FILE_ALIGNMENT_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_ALIGNMENT_INFORMATION, PFILE_ALIGNMENT_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_ALIGNMENT_INFORMATION, kernel.file_alignment_information, kstruct_b_ce42b00c-17a9-4fcf-a6bb-ade557580e81.xml, ntddk/FILE_ALIGNMENT_INFORMATION, ntddk/PFILE_ALIGNMENT_INFORMATION"
f1_keywords:
 - "ntddk/FILE_ALIGNMENT_INFORMATION"
 - "FILE_ALIGNMENT_INFORMATION"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- FILE_ALIGNMENT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_ALIGNMENT_INFORMATION, *PFILE_ALIGNMENT_INFORMATION
---

# _FILE_ALIGNMENT_INFORMATION structure


## -description


The <b>FILE_ALIGNMENT_INFORMATION</b> structure is used as an argument to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> routine.


## -struct-fields




### -field AlignmentRequirement

The buffer alignment required by the underlying device. For a list of system-defined values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>. The value must be one of the FILE_<i>XXX</i>_ALIGNMENT values defined in Wdm.h. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/initializing-a-device-object">Initializing a Device Object</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

