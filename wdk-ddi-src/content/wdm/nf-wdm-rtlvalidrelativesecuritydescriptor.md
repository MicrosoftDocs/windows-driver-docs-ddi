---
UID: NF:wdm.RtlValidRelativeSecurityDescriptor
title: RtlValidRelativeSecurityDescriptor function (wdm.h)
description: The RtlValidRelativeSecurityDescriptor routine checks the validity of a self-relative security descriptor.
old-location: kernel\rtlvalidrelativesecuritydescriptor.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlValidRelativeSecurityDescriptor function"]
ms.keywords: RtlValidRelativeSecurityDescriptor, RtlValidRelativeSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_b261fb47-147f-4e39-81fb-bdbc31d53681.xml, kernel.rtlvalidrelativesecuritydescriptor, wdm/RtlValidRelativeSecurityDescriptor
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlValidRelativeSecurityDescriptor
 - wdm/RtlValidRelativeSecurityDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlValidRelativeSecurityDescriptor
---

# RtlValidRelativeSecurityDescriptor function


## -description

The <b>RtlValidRelativeSecurityDescriptor</b> routine checks the validity of a self-relative security descriptor.

## -parameters

### -param SecurityDescriptorInput 

[in]
A pointer to the buffer that contains the security descriptor in self-relative format. The buffer must begin with a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure, which is followed by the rest of the security descriptor data.

### -param SecurityDescriptorLength 

[in]
The size of the <i>SecurityDescriptorInput</i> structure.

### -param RequiredInformation 

[in]
A <a href="/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a> value that specifies the information that is required to be contained in the security descriptor.

## -returns

<b>RtlValidRelativeSecurityDescriptor</b> returns <b>TRUE</b> if the security descriptor is valid and includes the information that the <i>RequiredInformation</i> parameter specifies. Otherwise, this routine returns <b>FALSE</b>.

## -remarks

To check the validity of a security descriptor in absolute format, use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a> instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a>
