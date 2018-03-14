---
UID: NS:d3dkmthk._D3DKMT_TRIMNOTIFICATION
title: "_D3DKMT_TRIMNOTIFICATION"
author: windows-driver-content
description: D3DKMT_TRIMNOTIFICATION is used to notify a driver to trim its memory residency list.
old-location: display\d3dkmt_trimnotification.htm
old-project: display
ms.assetid: 50E3F5CC-AFB9-4527-A812-44295373D80B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_TRIMNOTIFICATION, D3DKMT_TRIMNOTIFICATION structure [Display Devices], _D3DKMT_TRIMNOTIFICATION, d3dkmthk/D3DKMT_TRIMNOTIFICATION, display.d3dkmt_trimnotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_TRIMNOTIFICATION
product: Windows
targetos: Windows
req.typenames: D3DKMT_TRIMNOTIFICATION
---

# _D3DKMT_TRIMNOTIFICATION structure


## -description


<b>D3DKMT_TRIMNOTIFICATION</b> is used to notify a driver to trim its memory residency list.


## -syntax


````
typedef struct _D3DKMT_TRIMNOTIFICATION {
  VOID                          *Context;
  D3DDDI_TRIMRESIDENCYSET_FLAGS Flags;
  UINT64                        NumBytesToTrim;
} D3DKMT_TRIMNOTIFICATION;
````


## -struct-fields




### -field Context

[in] The caller-supplied context for the callback notification.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_trimresidencyset_flags.md">D3DDDI_TRIMRESIDENCYSET_FLAGS</a> structure containing the trimming behavior flags.


### -field NumBytesToTrim

[in] When <b>TrimToBudget</b> is set, this value specifies how much the application should evict in order to meet its current memory budget.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_trimresidencyset_flags.md">D3DDDI_TRIMRESIDENCYSET_FLAGS</a>



 

 


