---
UID: NF:wdm.MmProtectDriverSection
title: MmProtectDriverSection function (wdm.h)
description: The MmProtectDriverSection read-only protects a section of a loaded driver by using the services provided by the Virtual Secure Mode (VSM).  
old-location: kernel\mmprotectdriversection.htm
tech.root: kernel
ms.date: 12/17/2018
keywords: ["MmProtectDriverSection function"]
ms.keywords: MmProtectDriverSection, MmProtectDriverSection routine [Kernel-Mode Driver Architecture], kernel.mmprotectdriversection , wdm/MmProtectDriverSection
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Insider 19548.
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
 - MmProtectDriverSection
 - wdm/MmProtectDriverSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmProtectDriverSection
---

# MmProtectDriverSection function


## -description

The 
   <b>MmProtectDriverSection</b> read-only protects a section of a loaded driver by using the services provided by the Virtual Secure Mode (VSM).  

## -parameters

### -param AddressWithinSection

[in]
 A pointer to a valid data section belonging to a driver image. The data section should not be already executable, otherwise the API will fail with STATUS_INVALID_PAGE_PROTECTION. 

### -param Size

[in]
 This parameter is currently reserved for future usage and should be set to 0.


### -param Flags

[in]
 Specify the flags which controls the operation: 
 MM_PROTECT_DRIVER_SECTION_ALLOW_UNLOAD – Used to specify that the driver can still be unloaded after the section has been protected. 



## -returns

<b>MmProtectDriverSection</b> returns a NTSTATUS value which indicates the result of the operation:



<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation has been successfully completed and the driver section has been successfully protected

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
Virtual Secure Mode (VSM) is currently disabled so the function can’t protect the driver section.  

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid flags bitmask (or a non-zero size) has been specified. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PAGE_PROTECTION</b></dt>
</dl>
</td>
<td width="60%">
The driver’s section specified by an address contained in it is mapped through an invalid protection (executable sections are not supported) 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The specified section belongs to a driver that is not supported by this API (see Remarks). 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The specified section is discardable or contains gaps, which are not backed by any physical memory. This usually happen when a section alignment is larger than a page size.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALREADY_COMMITTED</b></dt>
</dl>
</td>
<td width="60%">
The specified section has been already protected. 

</tr>
</table>



## -remarks

The routine protects the physical memory backing the driver’s section using the SLAT table (second level address translation) managed by the VSM. The protected memory will be made read-only for the entire Operating System.  

Note that, after the section has been protected, there is no way to remove the protection. This is by design: the only exception of this rule is when the caller specifies the MM_PROTECT_DRIVER_SECTION_ALLOW_UNLOAD flag. In that case, when the target driver is unloaded, the protected section is released and freed. 

Drivers mapped with large pages and session drivers are not supported by the <b>MmProtectDriverSection</b> API. Furthermore, callers of this API can’t request to protect a discardable section or a section that contains the IAT (Import Address Table). 

Note that if the caller specifies an address that does not belong to any loaded driver image, the system will be crashed with the MEMORY_MANAGEMENT bugcheck (type 0x1100). 

Callers of the <b>MmProtectDriverSection</b> API should execute at IRQL <= APC_LEVEL. 