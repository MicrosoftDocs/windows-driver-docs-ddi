---
UID: NS:wpprecorder._WPP_TRIAGE_INFO
title: _WPP_TRIAGE_INFO
author: windows-driver-content
description: Used to locate the WPP log for WER reporting.
old-location: devtest\wpp_triage_info.htm
old-project: devtest
ms.assetid: BC2722A8-C09A-4C46-9EC3-45DCF4A6FD64
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WPP_TRIAGE_INFO
req.alt-loc: Wpprecorder.h
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
req.typenames: *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# _WPP_TRIAGE_INFO structure



## -description
Used to locate the WPP log
for WER reporting.



## -syntax

````
typedef struct _WPP_TRIAGE_INFO {
  ULONG WppAutoLogHeaderSize;
  ULONG WppDriverContextOffset;
  ULONG WppAutoLogHeaderSizeOffset;
  ULONG WppSizeOfAutoLogHeaderSizeField;
  ULONG WppDriverContextSize;
} WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO;
````


## -struct-fields

### -field WppAutoLogHeaderSize

Size of WPP_AUTOLOG_HEADER.


### -field WppDriverContextOffset

Offset of DriverContext into WPP_AUTOLOG_HEADER.


### -field WppAutoLogHeaderSizeOffset

Offset of Size field into WPP_AUTOLOG_HEADER.


### -field WppSizeOfAutoLogHeaderSizeField

 Size of Header size field.


### -field WppDriverContextSize

 Size of WPP_AUTOLOG_CONTEXT.


## -remarks
