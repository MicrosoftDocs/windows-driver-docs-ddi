---
UID: NF:wdfdriver.WdfGetDriver
title: WdfGetDriver function (wdfdriver.h)
description: The WdfGetDriver method returns a handle to the framework driver object that represents the calling driver.
old-location: wdf\wdfgetdriver.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfGetDriver function"]
ms.keywords: DFDriverObjectRef_7419a365-e5ee-49cd-8d85-4db65cd27645.xml, WdfGetDriver, WdfGetDriver method, kmdf.wdfgetdriver, wdf.wdfgetdriver, wdfdriver/WdfGetDriver
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfGetDriver
 - wdfdriver/WdfGetDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfGetDriver
---

# WdfGetDriver function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfGetDriver</b> method returns a handle to the framework driver object that represents the calling driver.

## -returns

<b>WdfGetDriver</b> returns a handle to a framework driver object, or <b>NULL</b> if the driver has not called <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>
