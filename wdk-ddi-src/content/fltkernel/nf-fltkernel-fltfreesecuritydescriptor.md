---
UID: NF:fltkernel.FltFreeSecurityDescriptor
title: FltFreeSecurityDescriptor function (fltkernel.h)
description: FltFreeSecurityDescriptor frees a security descriptor allocated by the FltBuildDefaultSecurityDescriptor routine.
old-location: ifsk\fltfreesecuritydescriptor.htm
tech.root: ifsk
ms.assetid: ebf7ad37-6c3b-4216-87e6-ea5d6a0cba20
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_ee21346e-6629-4ffd-bf82-b3915f4e1649.xml, FltFreeSecurityDescriptor, FltFreeSecurityDescriptor routine [Installable File System Drivers], fltkernel/FltFreeSecurityDescriptor, ifsk.fltfreesecuritydescriptor
f1_keywords:
 - "fltkernel/FltFreeSecurityDescriptor"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltFreeSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltFreeSecurityDescriptor function


## -description


<b>FltFreeSecurityDescriptor</b> frees a security descriptor allocated by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltbuilddefaultsecuritydescriptor">FltBuildDefaultSecurityDescriptor</a> routine. 


## -parameters




### -param SecurityDescriptor [in]

Opaque pointer to the security descriptor (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>) to be freed. 


## -returns



None 




## -remarks



<b>FltFreeSecurityDescriptor</b> should only be used to free a security descriptor that was allocated by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltbuilddefaultsecuritydescriptor">FltBuildDefaultSecurityDescriptor</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltbuilddefaultsecuritydescriptor">FltBuildDefaultSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
 

 

