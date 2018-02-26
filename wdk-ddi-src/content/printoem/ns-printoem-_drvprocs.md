---
UID: NS:printoem._DRVPROCS
title: "_DRVPROCS"
author: windows-driver-content
description: The DRVPROCS structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers.
old-location: print\drvprocs.htm
old-project: print
ms.assetid: fcdfb7ba-cbb4-454b-b366-82d0c95b4afd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PDRVPROCS, ,, C, D, DRVPROCS, DRVPROCS structure [Print Devices], O, P, PDRVPROCS, PDRVPROCS structure pointer [Print Devices], R, S, V, _, _DRVPROCS, print.drvprocs, print_unidrv-pscript_rendering_63cf2b11-04c8-43f3-951b-5755764059f9.xml, printoem/DRVPROCS, printoem/PDRVPROCS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	DRVPROCS
product: Windows
targetos: Windows
req.typenames: DRVPROCS, *PDRVPROCS
req.product: Windows 10 or later.
---

# _DRVPROCS structure


## -description


The DRVPROCS structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers.

The structure contains the addresses of helper functions that are provided to rendering plug-ins by Microsoft printer drivers.

All of the functions pointed to by members of this structure are obsolete. For information about each see:
<dl>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvwritespoolbuf.md">DrvWriteSpoolBuf</a>


</dd>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvxmoveto.md">DrvXMoveTo</a>


</dd>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvymoveto.md">DrvYMoveTo</a>


</dd>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvgetdriversetting.md">DrvGetDriverSetting</a>


</dd>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvgetstandardvariable.md">DrvGetStandardVariable</a> (for information about BGetStandardVariable)

</dd>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvunidrivertextout.md">DrvUnidriverTextOut</a>


</dd>
<dd>

<a href="..\printoem\nc-printoem-pfn_drvwriteabortbuf.md">DrvWriteAbortBuf</a>


</dd>
</dl>

## -syntax


````
typedef struct _DRVPROCS {
  PFN_DrvWriteSpoolBuf       DrvWriteSpoolBuf;
  PFN_DrvXMoveTo             DrvXMoveTo;
  PFN_DrvYMoveTo             DrvYMoveTo;
  PFN_DrvGetDriverSetting    DrvGetDriverSetting;
  PFN_DrvGetStandardVariable BGetStandardVariable;
  PFN_DrvUnidriverTextOut    DrvUnidriverTextOut;
  PFN_DrvWriteAbortBuf       DrvWriteAbortBuf;
} DRVPROCS, *PDRVPROCS;
````


## -struct-fields




### -field DrvWriteSpoolBuf


### -field DrvXMoveTo


### -field DrvYMoveTo


### -field DrvGetDriverSetting


### -field BGetStandardVariable


### -field DrvUnidriverTextOut


### -field DrvWriteAbortBuf

