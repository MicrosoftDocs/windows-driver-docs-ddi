---
UID: NF:fltkernel.FltFreeSecurityDescriptor
title: FltFreeSecurityDescriptor function
author: windows-driver-content
description: FltFreeSecurityDescriptor frees a security descriptor allocated by the FltBuildDefaultSecurityDescriptor routine.
old-location: ifsk\fltfreesecuritydescriptor.htm
old-project: ifsk
ms.assetid: ebf7ad37-6c3b-4216-87e6-ea5d6a0cba20
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_e_to_o_ee21346e-6629-4ffd-bf82-b3915f4e1649.xml, FltFreeSecurityDescriptor, FltFreeSecurityDescriptor routine [Installable File System Drivers], ifsk.fltfreesecuritydescriptor, fltkernel/FltFreeSecurityDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltFreeSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreeSecurityDescriptor function


## -description


<b>FltFreeSecurityDescriptor</b> frees a security descriptor allocated by the <a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a> routine. 


## -syntax


````
VOID FltFreeSecurityDescriptor(
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters




### -param SecurityDescriptor [in]

Opaque pointer to the security descriptor (<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>) to be freed. 


## -returns


None 



## -remarks


<b>FltFreeSecurityDescriptor</b> should only be used to free a security descriptor that was allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a>. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFreeSecurityDescriptor routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

