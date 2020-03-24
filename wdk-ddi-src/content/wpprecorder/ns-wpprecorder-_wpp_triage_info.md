---
UID: NS:wpprecorder._WPP_TRIAGE_INFO
title: _WPP_TRIAGE_INFO (wpprecorder.h)
description: Used to locate the WPP log for WER reporting.
old-location: devtest\wpp_triage_info.htm
tech.root: devtest
ms.assetid: BC2722A8-C09A-4C46-9EC3-45DCF4A6FD64
ms.date: 02/23/2018
keywords: ["_WPP_TRIAGE_INFO structure"]
ms.keywords: "*PWPP_TRIAGE_INFO, PWPP_TRIAGE_INFO, PWPP_TRIAGE_INFO structure pointer [Driver Development Tools], WPP_TRIAGE_INFO, WPP_TRIAGE_INFO structure [Driver Development Tools], _WPP_TRIAGE_INFO, devtest.wpp_triage_info, wpprecorder/PWPP_TRIAGE_INFO, wpprecorder/WPP_TRIAGE_INFO"
f1_keywords:
 - "wpprecorder/WPP_TRIAGE_INFO"
req.header: wpprecorder.h
req.include-header: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wpprecorder.h
api_name:
- WPP_TRIAGE_INFO
product:
- Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
---

# _WPP_TRIAGE_INFO structure


## -description


Used to locate the WPP log
for WER reporting.


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

