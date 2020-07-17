---
UID: NF:poscx.PosCxMarkPosApp
title: PosCxMarkPosApp function (poscx.h)
description: PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application.
old-location: pos\poscxmarkposapp.htm
tech.root: pos
ms.assetid: 6BFFD014-E9DC-495C-9810-0D23BD93C41A
ms.date: 02/23/2018
keywords: ["PosCxMarkPosApp function"]
ms.keywords: PosCxMarkPosApp, PosCxMarkPosApp function, pos.poscxmarkposapp, poscx/PosCxMarkPosApp
f1_keywords:
 - "poscx/PosCxMarkPosApp"
 - "PosCxMarkPosApp"
req.header: poscx.h
req.include-header: Poscx.h
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
- poscx.h
api_name:
- PosCxMarkPosApp
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxMarkPosApp function


## -description


PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application.

This optional method provides value if the driver implements multiple device interfaces. It helps to  identify which interface is currently in use.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

A handle to a framework file object that identifies the caller, usually acquired with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetfileobject">WdfRequestGetFileObject</a>.


### -param isPosApp [in]

Specifies if the open instance is associated with a point-of-service application. Set to TRUE if it is associated with a point-of-service application. Otherwise, set to FALSE.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>Completed successfully.</td>
</tr>
<tr>
<td><b>INVALID_PARAMETER</b></td>
<td>The specified <i>fileObject</i> is invalid.</td>
</tr>
</table>
 



