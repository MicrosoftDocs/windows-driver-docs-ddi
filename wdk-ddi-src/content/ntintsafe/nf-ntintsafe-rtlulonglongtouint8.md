---
UID: NF:ntintsafe.RtlULongLongToUInt8
title: RtlULongLongToUInt8 function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type UINT8.
old-location: kernel\rtlulonglongtouint8.htm
old-project: kernel
ms.assetid: 6A4A46EC-6B52-4A93-85FA-01DC87DD93B6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongLongToUInt8, kernel.rtlulonglongtouint8, RtlULongLongToUInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongLongToUInt8
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
-	RtlULongLongToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongLongToUInt8 function


## -description


Converts a value of type <b>ULONGLONG</b> to a value of type <b>UINT8</b>.


## -syntax


````
NTSTATUS RtlULongLongToUInt8(
  _In_  ULONGLONG ullOperand,
  _Out_ UINT8     *pu8Result
);
````


## -parameters




### -param ullOperand [in]

The value to be converted.


### -param pu8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks


This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


