---
UID: NE:wdm._ENLISTMENT_INFORMATION_CLASS
title: _ENLISTMENT_INFORMATION_CLASS (wdm.h)
description: The ENLISTMENT_INFORMATION_CLASS enumeration identifies the type of information that the ZwSetInformationEnlistment routine can set and that the ZwQueryInformationEnlistment routine can retrieve for an enlistment object.
old-location: kernel\enlistment_information_class.htm
tech.root: kernel
ms.assetid: d031e032-66e3-4697-8db1-67655cfc223d
ms.date: 04/30/2018
keywords: ["ENLISTMENT_INFORMATION_CLASS enumeration"]
ms.keywords: ENLISTMENT_INFORMATION_CLASS, ENLISTMENT_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], EnlistmentBasicInformation, EnlistmentCrmInformation, EnlistmentRecoveryInformation, _ENLISTMENT_INFORMATION_CLASS, kernel.enlistment_information_class, ktm_ref_9bf2b9fa-5b9a-47fb-873c-6bd5f1930553.xml, wdm/ENLISTMENT_INFORMATION_CLASS, wdm/EnlistmentBasicInformation, wdm/EnlistmentCrmInformation, wdm/EnlistmentRecoveryInformation
f1_keywords:
 - "wdm/ENLISTMENT_INFORMATION_CLASS"
 - "ENLISTMENT_INFORMATION_CLASS"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
- ENLISTMENT_INFORMATION_CLASS
targetos: Windows
req.typenames: ENLISTMENT_INFORMATION_CLASS
---

# _ENLISTMENT_INFORMATION_CLASS enumeration


## -description


The <b>ENLISTMENT_INFORMATION_CLASS</b> enumeration identifies the type of information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a> routine can set and that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a> routine can retrieve for an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>.


## -enum-fields




### -field EnlistmentBasicInformation

Information about an enlistment object is stored in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_enlistment_basic_information">ENLISTMENT_BASIC_INFORMATION</a> structure.


### -field EnlistmentRecoveryInformation

A resource manager is setting or obtaining customized recovery information for an enlistment. To learn more about recovery information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>.


### -field EnlistmentCrmInformation

Information about an enlistment object is stored in an <b>ENLISTMENT_CRM_INFORMATION</b> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_enlistment_basic_information">ENLISTMENT_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>
 

 

