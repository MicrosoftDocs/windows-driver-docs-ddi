---
UID: NE:wudfddi._SECURITY_IMPERSONATION_LEVEL
title: "_SECURITY_IMPERSONATION_LEVEL"
author: windows-driver-content
description: The SECURITY_IMPERSONATION_LEVEL enumeration contains values that identify security impersonation levels.
old-location: wdf\security_impersonation_level.htm
tech.root: wdf
ms.assetid: 5c325c16-6bc6-4eae-a58c-234d11616780
ms.date: 2/26/2018
ms.keywords: SECURITY_IMPERSONATION_LEVEL, SECURITY_IMPERSONATION_LEVEL enumeration, SecurityAnonymous, SecurityDelegation, SecurityIdentification, SecurityImpersonation, _SECURITY_IMPERSONATION_LEVEL, umdf.security_impersonation_level, umdfstructs_f81ccb0e-4b8c-4a8a-bdd3-4b4a45a750ab.xml, wdf.security_impersonation_level, wudfddi/SECURITY_IMPERSONATION_LEVEL, wudfddi/SecurityAnonymous, wudfddi/SecurityDelegation, wudfddi/SecurityIdentification, wudfddi/SecurityImpersonation
ms.topic: enum
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi.h
api_name:
-	SECURITY_IMPERSONATION_LEVEL
product:
- Windows
targetos: Windows
req.typenames: SECURITY_IMPERSONATION_LEVEL
---

# _SECURITY_IMPERSONATION_LEVEL enumeration


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>SECURITY_IMPERSONATION_LEVEL</b> enumeration contains values that identify security impersonation levels.


## -enum-fields




### -field SecurityAnonymous

The driver cannot impersonate or identify the client.


### -field SecurityIdentification

The driver can obtain the identity and privileges of the client but cannot impersonate the client.


### -field SecurityImpersonation

The driver can impersonate the client's security context on the local system.


### -field SecurityDelegation

The driver can impersonate the client's security context on remote systems.


## -remarks



For more information about impersonation in the UMDF, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Client Impersonation</a>.

A UMDF driver supplies one of the values of <b>SECURITY_IMPERSONATION_LEVEL</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a> method to set the security impersonation level.

For more information about the security impersonation levels, see the <b>SECURITY_IMPERSONATION_LEVEL</b> enumeration type in the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>
 

 

