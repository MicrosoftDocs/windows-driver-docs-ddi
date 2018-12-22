---
UID: NS:wdm._RESOURCEMANAGER_BASIC_INFORMATION
title: "_RESOURCEMANAGER_BASIC_INFORMATION"
description: The RESOURCEMANAGER_BASIC INFORMATION structure contains information about a resource manager object.
old-location: kernel\resourcemanager_basic_information.htm
tech.root: kernel
ms.assetid: b5295760-7f0e-4973-9ce3-4aa35ea5211b
ms.date: 04/30/2018
ms.keywords: "*PRESOURCEMANAGER_BASIC_INFORMATION, PRESOURCEMANAGER_BASIC_INFORMATION, PRESOURCEMANAGER_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], RESOURCEMANAGER_BASIC_INFORMATION, RESOURCEMANAGER_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], _RESOURCEMANAGER_BASIC_INFORMATION, kernel.resourcemanager_basic_information, ktm_ref_bcc9f19b-2cd4-45da-b5df-1f28e832d48e.xml, wdm/PRESOURCEMANAGER_BASIC_INFORMATION, wdm/RESOURCEMANAGER_BASIC_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
-	Wdm.h
api_name:
-	RESOURCEMANAGER_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: RESOURCEMANAGER_BASIC_INFORMATION, *PRESOURCEMANAGER_BASIC_INFORMATION
---

# _RESOURCEMANAGER_BASIC_INFORMATION structure


## -description


The <b>RESOURCEMANAGER_BASIC INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -struct-fields




### -field ResourceManagerId

A GUID that KTM assigned to the resource manager.


### -field DescriptionLength

The length, in bytes, of the character array that the <b>Description</b> member provides.


### -field Description

A caller-allocated array of characters that receives a resource manager's description string. 


## -remarks



The <b>RESOURCEMANAGER_BASIC INFORMATION</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567054">ZwQueryInformationResourceManager</a> routine.

The resource manager's description string, which the <b>Description</b> member receives, is the description that the resource manager previously specified when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567054">ZwQueryInformationResourceManager</a>
 

 

