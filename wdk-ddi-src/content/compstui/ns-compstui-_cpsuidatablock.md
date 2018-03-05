---
UID: NS:compstui._CPSUIDATABLOCK
title: "_CPSUIDATABLOCK"
author: windows-driver-content
description: The CPSUIDATABLOCK structure is used as a parameter for the ComPropSheet function, if the function code is CPSFUNC_SET_DATABLOCK or CPSFUNC_QUERY_DATABLOCK.
old-location: print\cpsuidatablock.htm
old-project: print
ms.assetid: c5b488ac-dd8d-4484-81ca-b64fdf517100
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCPSUIDATABLOCK, CPSUIDATABLOCK, CPSUIDATABLOCK structure [Print Devices], PCPSUIDATABLOCK, PCPSUIDATABLOCK structure pointer [Print Devices], _CPSUIDATABLOCK, compstui/CPSUIDATABLOCK, compstui/PCPSUIDATABLOCK, cpsuifnc_c9e406f5-1d6a-403d-a286-89cf199a09d2.xml, print.cpsuidatablock"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	compstui.h
api_name:
-	CPSUIDATABLOCK
product: Windows
targetos: Windows
req.typenames: CPSUIDATABLOCK, *PCPSUIDATABLOCK
---

# _CPSUIDATABLOCK structure


## -description


The CPSUIDATABLOCK structure is used as a parameter for the <a href="..\compstui\nc-compstui-pfncompropsheet.md">ComPropSheet</a> function, if the function code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff547036">CPSFUNC_SET_DATABLOCK</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546425">CPSFUNC_QUERY_DATABLOCK</a>.


## -syntax


````
typedef struct _CPSUIDATABLOCK {
  DWORD  cbData;
  LPBYTE pbData;
} CPSUIDATABLOCK, *PCPSUIDATABLOCK;
````


## -struct-fields




### -field cbData

Size, in bytes of the buffer pointed to by <b>pbData</b>.


### -field pbData

Pointer to a caller-allocated buffer.

