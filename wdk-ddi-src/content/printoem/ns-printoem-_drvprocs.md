---
UID: NS:printoem._DRVPROCS
title: _DRVPROCS (printoem.h)
description: The DRVPROCS structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers.
old-location: print\drvprocs.htm
tech.root: print
ms.assetid: fcdfb7ba-cbb4-454b-b366-82d0c95b4afd
ms.date: 04/20/2018
ms.keywords: "*PDRVPROCS, DRVPROCS, DRVPROCS structure [Print Devices], PDRVPROCS, PDRVPROCS structure pointer [Print Devices], _DRVPROCS, print.drvprocs, print_unidrv-pscript_rendering_63cf2b11-04c8-43f3-951b-5755764059f9.xml, printoem/DRVPROCS, printoem/PDRVPROCS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	DRVPROCS
product:
- Windows
targetos: Windows
req.typenames: DRVPROCS, *PDRVPROCS
---

# _DRVPROCS structure


## -description


The DRVPROCS structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers.

The structure contains the addresses of helper functions that are provided to rendering plug-ins by Microsoft printer drivers.

All of the functions pointed to by members of this structure are obsolete. For information about each see:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548662">DrvWriteSpoolBuf</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548665">DrvXMoveTo</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548673">DrvYMoveTo</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548556">DrvGetDriverSetting</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548562">DrvGetStandardVariable</a> (for information about BGetStandardVariable)

</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548638">DrvUnidriverTextOut</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548657">DrvWriteAbortBuf</a>


</dd>
</dl>

## -struct-fields




### -field DrvWriteSpoolBuf


### -field DrvXMoveTo


### -field DrvYMoveTo


### -field DrvGetDriverSetting


### -field BGetStandardVariable


### -field DrvUnidriverTextOut


### -field DrvWriteAbortBuf

