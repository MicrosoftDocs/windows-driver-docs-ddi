---
UID: NS:wdm._REG_SET_KEY_SECURITY_INFORMATION
title: "_REG_SET_KEY_SECURITY_INFORMATION"
author: windows-driver-content
description: The REG_SET_KEY_SECURITY_INFORMATION structure specifies security information for a registry key object.
old-location: kernel\reg_set_key_security_information.htm
old-project: kernel
ms.assetid: 196bad19-85a6-41a0-ac61-b70594a19f0f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PREG_SET_KEY_SECURITY_INFORMATION, ,, A, C, E, F, G, I, K, M, N, O, P, PREG_SET_KEY_SECURITY_INFORMATION, PREG_SET_KEY_SECURITY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, REG_SET_KEY_SECURITY_INFORMATION, REG_SET_KEY_SECURITY_INFORMATION structure [Kernel-Mode Driver Architecture], S, T, U, Y, _, _REG_SET_KEY_SECURITY_INFORMATION, kernel.reg_set_key_security_information, kstruct_d_2154cf21-9f72-488b-ad13-687ada458991.xml, wdm/PREG_SET_KEY_SECURITY_INFORMATION, wdm/REG_SET_KEY_SECURITY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	REG_SET_KEY_SECURITY_INFORMATION
product: Windows
targetos: Windows
req.typenames: REG_SET_KEY_SECURITY_INFORMATION, *PREG_SET_KEY_SECURITY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_SET_KEY_SECURITY_INFORMATION structure


## -description


The <b>REG_SET_KEY_SECURITY_INFORMATION</b> structure specifies security information for a registry key object.


## -syntax


````
typedef struct _REG_SET_KEY_SECURITY_INFORMATION {
  PVOID                 Object;
  PSECURITY_INFORMATION SecurityInformation;
  PSECURITY_DESCRIPTOR  SecurityDescriptor;
  PVOID                 CallContext;
  PVOID                 ObjectContext;
  PVOID                 Reserved;
} REG_SET_KEY_SECURITY_INFORMATION, *PREG_SET_KEY_SECURITY_INFORMATION;
````


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose security information is being set.


### -field SecurityInformation

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>-typed variable that identifies the type of security information that is being set.


### -field SecurityDescriptor

A pointer to a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure that contains security information for the key object.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



The system passes the <b>REG_SET_KEY_SECURITY_INFORMATION</b> structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to set a key's security information—for example, when a driver calls <a href="..\ntifs\nf-ntifs-zwsetsecurityobject.md">ZwSetSecurityObject</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="..\ntifs\nf-ntifs-zwsetsecurityobject.md">ZwSetSecurityObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_SET_KEY_SECURITY_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

