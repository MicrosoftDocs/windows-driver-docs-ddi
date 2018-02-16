---
UID: NF:ntifs.SeTokenGetNoChildProcessRestricted
title: SeTokenGetNoChildProcessRestricted function
author: windows-driver-content
description: The SeTokenGetNoChildProcessRestricted routine determines the state of the no child process mitigation. It is not possible to be enforced and audit-only at the same time.
old-location: ifsk\setokengetnochildprocessrestricted.htm
old-project: ifsk
ms.assetid: 6C42E6C4-91EB-44A3-84E1-CAFDBD5CD724
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: SeTokenGetNoChildProcessRestricted, ntifs/SeTokenGetNoChildProcessRestricted, ifsk.setokengetnochildprocessrestricted, SeTokenGetNoChildProcessRestricted function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeTokenGetNoChildProcessRestricted
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeTokenGetNoChildProcessRestricted function


## -description


The <b>SeTokenGetNoChildProcessRestricted</b> routine determines the state of the no child process mitigation.  It is
    not possible to be enforced and audit-only at the same time.


## -syntax


````
void NTKERNELAPI SeTokenGetNoChildProcessRestricted(
  _In_  PACCESS_TOKEN Token,
  _Out_ PBOOLEAN      Enforced,
  _Out_ PBOOLEAN      UnlessSecure,
  _Out_ PBOOLEAN      AuditOnly
);
````


## -parameters




### -param Token [in]

Specifies a pointer to the access token.


### -param Enforced [out]

A pointer to a boolean that returns whether the mitigation is in enforcement mode.


### -param UnlessSecure [out]

A pointer to a boolean that returns whether secure process creation is enabled even if
        process creation is restricted.


### -param AuditOnly [out]

A pointer to a boolean that returns whether the mitigation is in audit-only mode.


## -returns



This function does not return a value.




## -see-also

<a href="..\ntifs\nf-ntifs-setokensetnochildprocessrestricted.md">SeTokenSetNoChildProcessRestricted</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeTokenGetNoChildProcessRestricted function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

