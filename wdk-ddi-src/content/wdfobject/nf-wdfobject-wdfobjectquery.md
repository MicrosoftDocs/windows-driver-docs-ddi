---
UID: NF:wdfobject.WdfObjectQuery
title: WdfObjectQuery function
author: windows-driver-content
description: The WdfObjectQuery method is not implemented.
old-location: wdf\wdfobjectquery.htm
old-project: wdf
ms.assetid: c9e654cc-7ea5-41dd-8ee5-23a89f61e3c1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfObjectQuery method, kmdf.wdfobjectquery, PFN_WDFOBJECTQUERY, WdfObjectQuery, wdfobject/WdfObjectQuery, DFGenObjectRef_1291f90f-1783-4bd6-ae7a-5481f3959628.xml, wdf.wdfobjectquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Not applicable
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdfobject.h
apiname: 
-	WdfObjectQuery
product: Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectQuery function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectQuery</b> method is not implemented.


## -syntax


````
NTSTATUS WdfObjectQuery(
  _In_  WDFOBJECT  Object,
  _In_  CONST GUID *Guid,
  _In_  ULONG      QueryBufferLength,
  _Out_ PVOID      QueryBuffer
);
````


## -parameters




### -param Object [in]



### -param Guid [in]



### -param QueryBufferLength [in]



### -param QueryBuffer [out]


