---
UID: NS:wdm._ENLISTMENT_BASIC_INFORMATION
title: _ENLISTMENT_BASIC_INFORMATION (wdm.h)
description: The ENLISTMENT_BASIC_INFORMATION structure contains information about an enlistment object.
old-location: kernel\enlistment_basic_information.htm
tech.root: kernel
ms.assetid: 50c989b9-147c-41ea-b933-3a3e8575563e
ms.date: 04/30/2018
keywords: ["_ENLISTMENT_BASIC_INFORMATION structure"]
ms.keywords: "*PENLISTMENT_BASIC_INFORMATION, ENLISTMENT_BASIC_INFORMATION, ENLISTMENT_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], PENLISTMENT_BASIC_INFORMATION, PENLISTMENT_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _ENLISTMENT_BASIC_INFORMATION, kernel.enlistment_basic_information, ktm_ref_5748a3a5-6a2a-4cf1-a610-2a406161b689.xml, wdm/ENLISTMENT_BASIC_INFORMATION, wdm/PENLISTMENT_BASIC_INFORMATION"
f1_keywords:
 - "wdm/ENLISTMENT_BASIC_INFORMATION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- ENLISTMENT_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: ENLISTMENT_BASIC_INFORMATION, *PENLISTMENT_BASIC_INFORMATION
---

# _ENLISTMENT_BASIC_INFORMATION structure


## -description


The <b>ENLISTMENT_BASIC_INFORMATION</b> structure contains information about an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>.


## -struct-fields




### -field EnlistmentId

A GUID that KTM has assigned to the enlistment object.


### -field TransactionId

A GUID that KTM has assigned to the transaction object that is associated with the enlistment object that the <b>EnlistmentId</b> member identifies.


### -field ResourceManagerId

A GUID that KTM has assigned to the resource manager that created the enlistment.


## -remarks



The <b>ENLISTMENT_BASIC INFORMATION</b> structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_enlistment_information_class">ENLISTMENT_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a>
 

 

