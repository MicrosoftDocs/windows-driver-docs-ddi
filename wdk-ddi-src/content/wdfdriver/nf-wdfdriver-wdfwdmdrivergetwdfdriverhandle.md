---
UID: NF:wdfdriver.WdfWdmDriverGetWdfDriverHandle
title: WdfWdmDriverGetWdfDriverHandle function
author: windows-driver-content
description: The WdfWdmDriverGetWdfDriverHandle method returns a handle to the framework driver object that is associated with a specified Windows Driver Model (WDM) driver object.
old-location: wdf\wdfwdmdrivergetwdfdriverhandle.htm
old-project: wdf
ms.assetid: 2126d36c-42c1-4e29-bf82-9f5682482557
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDriverObjectRef_9cf5a70f-e2df-4302-9558-c8cd066cf8e4.xml, WdfWdmDriverGetWdfDriverHandle, WdfWdmDriverGetWdfDriverHandle method, kmdf.wdfwdmdrivergetwdfdriverhandle, wdf.wdfwdmdrivergetwdfdriverhandle, wdfdriver/WdfWdmDriverGetWdfDriverHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfWdmDriverGetWdfDriverHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWdmDriverGetWdfDriverHandle function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWdmDriverGetWdfDriverHandle</b> method returns a handle to the framework driver object that is associated with a specified Windows Driver Model (WDM) driver object.


## -parameters




### -param DriverObject [in]

A pointer to a WDM driver object.


## -returns



<b>WdfWdmDriverGetWdfDriverHandle</b> returns a handle to a framework driver object. A system bug check occurs if the <i>DriverObject</i> pointer is <b>NULL</b>. 



