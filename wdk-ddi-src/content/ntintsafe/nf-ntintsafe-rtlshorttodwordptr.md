---
UID: NF:ntintsafe.RtlShortToDWordPtr
title: RtlShortToDWordPtr function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type DWORD_PTR.
old-location: kernel\rtlshorttodwordptr.htm
old-project: kernel
ms.assetid: 0ABB3DBF-117D-491D-85A3-68E9280CFC6C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlShortToDWordPtr, kernel.rtlshorttodwordptr, RtlShortToDWordPtr function [Kernel-Mode Driver Architecture], RtlShortToDWordPtr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlShortToDWordPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlShortToDWordPtr function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>DWORD_PTR</b>.


## -syntax


````
NTSTATUS RtlShortToDWordPtr(
  _In_  SHORT     sOperand,
  _Out_ DWORD_PTR *pdwResult
);
````


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pdwResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li></li>
</ul>

