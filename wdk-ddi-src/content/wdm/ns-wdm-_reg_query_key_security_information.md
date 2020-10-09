---
UID: NS:wdm._REG_QUERY_KEY_SECURITY_INFORMATION
title: _REG_QUERY_KEY_SECURITY_INFORMATION (wdm.h)
description: The REG_QUERY_KEY_SECURITY_INFORMATION structure receives security information for a registry key object.
old-location: kernel\reg_query_key_security_information.htm
tech.root: kernel
ms.assetid: 8bfe793d-c902-4459-98eb-e134759efc48
ms.date: 04/30/2018
keywords: ["REG_QUERY_KEY_SECURITY_INFORMATION structure"]
ms.keywords: "*PREG_QUERY_KEY_SECURITY_INFORMATION, PREG_QUERY_KEY_SECURITY_INFORMATION, PREG_QUERY_KEY_SECURITY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_QUERY_KEY_SECURITY_INFORMATION, REG_QUERY_KEY_SECURITY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_QUERY_KEY_SECURITY_INFORMATION, kernel.reg_query_key_security_information, kstruct_d_952b1831-9ce9-4f9e-8669-02480c0ad3a0.xml, wdm/PREG_QUERY_KEY_SECURITY_INFORMATION, wdm/REG_QUERY_KEY_SECURITY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
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
req.typenames: REG_QUERY_KEY_SECURITY_INFORMATION, *PREG_QUERY_KEY_SECURITY_INFORMATION
f1_keywords:
 - _REG_QUERY_KEY_SECURITY_INFORMATION
 - wdm/_REG_QUERY_KEY_SECURITY_INFORMATION
 - PREG_QUERY_KEY_SECURITY_INFORMATION
 - wdm/PREG_QUERY_KEY_SECURITY_INFORMATION
 - REG_QUERY_KEY_SECURITY_INFORMATION
 - wdm/REG_QUERY_KEY_SECURITY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - REG_QUERY_KEY_SECURITY_INFORMATION
---

# _REG_QUERY_KEY_SECURITY_INFORMATION structure


## -description

The <b>REG_QUERY_KEY_SECURITY_INFORMATION</b> structure receives security information for a registry key object.

## -struct-fields

### -field Object

A pointer to the registry key object for the key whose security information is being retrieved.

### -field SecurityInformation

A pointer to a <a href="/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a>-typed value that identifies the type of security information that is being requested.

### -field SecurityDescriptor

A pointer to a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure that receives security information for the key object.

### -field Length

The length, in bytes of the <b>SECURITY_DESCRIPTOR</b> structure that <b>SecurityDescriptor</b> points to.

### -field CallContext

Optional driver-defined context information that the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## -remarks

The system passes the <b>REG_QUERY_KEY_SECURITY_INFORMATION</b> structure to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to query a key's security information—for example, when a driver calls <a href="/previous-versions/ff567066(v=vs.85)">ZwQuerySecurityObject</a>.

For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a>



<a href="/previous-versions/ff567066(v=vs.85)">ZwQuerySecurityObject</a>